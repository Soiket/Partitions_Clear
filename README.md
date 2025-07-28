# Partitions_Clear
For remove partions
   89  sudo umount /dev/vdh* /dev/vdg* /dev/vdf* 2>/dev/null
   90  sudo lvdisplay
   91  sudo lvremove -y /dev/mapper/ceph-*
   92  sudo vgremove -y ceph-*
   93  sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf
   94  sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf --force
   95  sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf --force --force
   96  for disk in /dev/vdf /dev/vdg /dev/vdh; do   echo "Wiping $disk";   sudo wipefs --all $disk;   sudo dd if=/dev/zero of=$disk bs=1M count=100; done
