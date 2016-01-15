# LxcMultiClone

`lxc-clone -s -B overlay` fails to provide multiple layers of overlays

Say you have container
`uu` which has vanilla ubuntu
`uuj` which is a clone of `uu` but with java
`uujhdp` which is a clone of `uuj` but with hadoop

`lxc-clone` of an existing overlayfs copies the entire `delta0`. Here it is avoided


Usage:
 copy the `myclone` and `mount-fs` to `/var/lib/lxc`
and from `/var/lib/lxc` execute
```
./myclone uu uuj
lxc-start -n uuj -F
# Install java into uuj
./myclone uuj uuhdp
# Install hadoop into uuj
```
  
