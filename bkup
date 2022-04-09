# specify working vars
stime="$(date +"%Y-%m-%d_%H-%M-%S")"
tmpdir="/tmp"
bkdir="/srv/dev-disk-by-id-md-name-OMV-DATA/docker"
loc="google:/backup"
archive="$tmpdir/docker.$stime.tar.gz"
log="/srv/dev-disk-by-id-md-name-OMV-DATA/Tmp"
rconf="/etc/rclone.conf"
ropt="-L -P -vv -u"

echo "current time is $time"
echo "start making tar archive"

# make archive
sudo tar cvzf $archive $bkdir

#set finish time
ftime="$(date +"%Y-%m-%d_%H-%M-%S")"
echo "finised archive at $ftime"

# upload to cloud with rclone
sudo rclone copy $archive $loc $ropt --config="$rconf" --log-file $log/BKSH.gdri                                                                                                                                                             ve.rclone.$ftime.log

echo "finished upload at $(date +"%Y-%m-%d_%H-%M-%S")"
echo "weather it failded or not"
echo "deleting archive file"

#remove archive file
sudo rm $archive
