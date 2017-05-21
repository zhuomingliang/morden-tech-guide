自动增量流备份：
#!/usr/bin/env sh

database2_user=root
database2_password=
database2="db1 db2"

database1_user=root
database1_password=
database1=db1

backup_host=192.168.1.2

week=$(date +\%U)
year=$(date +\%Y)


if [ $(date +\%w) -eq "0" ]; then

    echo $(date +\%Y-\%m-\%d) is $(date +\%A), do full backup of $database2.
    # innobackupex --user=$database2_user --password=$database2_password --socket=/var/run/mysqld/mysqld-3307.sock --databases="$database2" --defaults-group=mysqld2 --history=$year-$week /data/backup/passport_and_ptgame/$year-$week
    innobackupex --user=$database2_user --password=$database2_password --socket=/var/run/mysqld/mysqld-3307.sock --databases="$database2" --defaults-group=mysqld2 --history=$year-$week --compress --compress-threads=8 --stream=xbstream --parallel=4 ./ | ssh dbbackup@$backup_host "mkdir -p passport_and_ptgame/$year-$week; cat - > ./passport_and_ptgame/$year-$week/$(date +\%Y-\%m-\%d-\%H-\%M-\%S).xbstream"

    echo $(date +\%Y-\%m-\%d) is $(date +\%A), do full backup of $database1.
    # innobackupex --user=$database1_user --password=$database1_password --socket=/var/run/mysqld/mysqld.sock --databases="$database1" --defaults-group=mysqld1 --history=$year-$week /data/backup/hgame/$year-$week
    innobackupex --user=$database1_user --password=$database1_password --socket=/var/run/mysqld/mysqld.sock --databases="$database1" --defaults-group=mysqld1 --history=$year-$week --compress --compress-threads=8 --stream=xbstream --parallel=4 ./ | ssh dbbackup@$backup_host "mkdir -p hgame/$year-$week; cat - > ./hgame/$year-$week/$(date +\%Y-\%m-\%d-\%H-\%M-\%S).xbstream"
else

    echo $(date +\%Y-\%m-\%d) is $(date +\%A), do incremental backup of $database2.
    # innobackupex --user=$database2_user --password=$database2_password --socket=/var/run/mysqld/mysqld-3307.sock --databases="$database2" --defaults-group=mysqld2 --history=$year-$week --incremental --incremental-history-name=$year-$week /data/backup/passport_and_ptgame/$year-$week
    innobackupex --user=$database2_user --password=$database2_password --socket=/var/run/mysqld/mysqld-3307.sock --databases="$database2" --defaults-group=mysqld2 --history=$year-$week --incremental --incremental-history-name=$year-$week --compress --compress-threads=8 --stream=xbstream --parallel=4 ./ | ssh dbbackup@$backup_host "cat - > ./passport_and_ptgame/$year-$week/$(date +\%Y-\%m-\%d-\%H-\%M-\%S).xbstream"

    echo $(date +\%Y-\%m-\%d) is $(date +\%A), do incremental backup of $database1.
    # innobackupex --user=$database1_user --password=$database1_password --socket=/var/run/mysqld/mysqld.sock --databases="$database1" --defaults-group=mysqld1 --history=$year-$week --incremental --incremental-history-name=$year-$week /data/backup/hgame/$year-$week
    innobackupex --user=$database1_user --password=$database1_password --socket=/var/run/mysqld/mysqld.sock --databases="$database1" --defaults-group=mysqld1 --history=$year-$week --incremental --incremental-history-name=$year-$week --compress --compress-threads=8 --stream=xbstream --parallel=4 ./ | ssh dbbackup@$backup_host "cat - > ./hgame/$year-$week/$(date +\%Y-\%m-\%d-\%H-\%M-\%S).xbstream"
fi
