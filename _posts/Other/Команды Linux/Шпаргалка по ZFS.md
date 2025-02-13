
modinfo zfs | head -n 9 - узнать версию ZFS и другие подробности

Информация о пулах / файловых системах (ФС) на пулах
zpool list - статус пулов
zpool status -v - статус пулов подробный
zfs list - список ФС, так называются монтируемые разделы в пулах
zfs get all - вся инфа по пулам, вообще вся

Управление пулами / дисками
ls -lha /dev/disk/by-id/ - выяснить айдишники дисков чтобы потом на них создать пул (будут проблемы если подцепишь по буквенному названию диска типа sda, они динамически меняются)
zpool create zfspool disk-id-1 disk-id-2 - может быть сколько угодно дисков, с ключом -f форсить создание пула
zpool create -m /mnt/backups zfspool disk-id-1 - создать пул с указанием папки маунтирования
zpool destroy zfspool - уничтожить пул zfspool, с ключом -f форсить уничтожение
mkfile 100m disk1 disk2 - создать файлы дисков
zpool create backups /disk1 /disk2- создать пул backups на созданных файлах
zpool create zfspool mirror /disk1 /disk2 - создать пул zfspool с зеркалированием на 2 диска
zpool add zfspool /disk3 - добавить диск в пул
zpool attach zfspool /disk3 - добавить устройство в пул, если он в зеркале то станет в зеркало, если простой, то пул расширится
zpool remove zfspool mirror-1
zpool detach zfspool /disk3 - исключить устройство из пула
zpool remove zfspool /disk3 - удаление устройства из пула
zpool add zfspool spare /disk3 - добавление диска горячей замены в пул
zpool remove zfspool spare /disk3 - удаление диска горячей замены из пула
zpool offline zfspool /disk1 - отключить устройство, на него не будет никакой записи и с него чтения, если добавить ключ -t, то после ребута станет онлайн
zpool online zfspool /disk1 - включить disk1
zpool replace zfspool /disk1 /disk3 - заменить disk 1, например в случае неисправности на disk3
zpool upgrade -v - увидеть версию, и фичи текущего ZFS, -a обновит все пулы до новейшей версии

Создание ФС и свойства ФС
zfs create zfspool/data - создать ФС data
zfs create zfspool/backups создать ФС backups, обе ФС будут бесконтрольно расти, пока не выставлены квоты
zfs destroy -fr zfspool/backups/old - уничтожит ФС old, ключ -r - рекурсивно, если внутри ещё несколько ФС, -f - форсить

zfs set reservation=1G zfspool/data - зарезервировать 1 Гигабайт, который ФС гарантированно получит, а другие не займут
zfs list -o quota zfspool/backups - выяснить квоту в пуле на ФС backups

zfs set quota=1G zfspool/backups - установить квоту в 1 Гигабайт на ФС backups
zfs list -o compression - проверить включена компрессия или нет

zfs set compression=on zfspool/backups - включить компрессию на ФС backups в пуле zfspool

zfs set sharesmb=on zfspool/backups - расшарить по SMB ФС backups средствами ZFS
zfs set sharenfs=on zfspool/backups - расшарить по NFS ФС backups средствами ZFS

Маунт
zfs mount - отобразить все маунтированные ФС
zfs mount zfspool/backups - маунт ФС backups
zfs umount zfspool/backups - анмаунт ФС backups
zfs mount -a - маунт всех ФС ZFS
zfs umount -a Umount - анмаунт всех ФС ZFS

Снапшоты
zfs list -t snapshot - отобразить все снапшоты
zfs list -o space - сколько занимают места снапшоты и конкретные дети пулов
zfs snapshot zfspool/backups@test - создать снапшот ФС backups с названием test
zfs rollback zfspool/backups@test - вернуться к снапшоту backups с названием test, с ключом -r рекурсивно уничтожит промежуточные снапшоты, с ключом -f форсит анмаунт и ремаунт
zfs destroy zfspool/backups@test - уничтожить снапшот backups с названием test
zfs send zfspool/backups@march2021 > /home/backups/march2021.bak - сделать локальный бекап снапшота march2021
zfs receive zfspool2/backups2 < /home/backups/march2021.bak - Восстановить из локального снапшота ФС на другом пуле
zfs send zfspool/backups@march2021 | zfs receive zfspool2/backups2 - Комбо предыдущих двух
zfs send zfspool/backups@march2021 | ssh COMP02 “zfs receive testpool/testfs” - Отправить снапшот по SSH на хост COMP02
zfs clone zfspool/backups@march2021 /clones/backups - Клонировать существующий снапшот
zfs destroy zfspool/backups@march2021 - Уничтожить клон

@linuxchmod
