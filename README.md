# Partitions_Clear
For remove partions
     sudo umount /dev/vdh* /dev/vdg* /dev/vdf* 2>/dev/null
     sudo lvdisplay
     sudo lvremove -y /dev/mapper/ceph-*
     sudo vgremove -y ceph-*
     sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf
     sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf --force
     sudo pvremove -y /dev/vdg /dev/vdh /dev/vdf --force --force
     for disk in /dev/vdf /dev/vdg /dev/vdh; do   echo "Wiping $disk";   sudo wipefs --all $disk;   sudo dd if=/dev/zero of=$disk bs=1M count=100; done
