The QRCodeReader depends on Rvtk  to build.  Please follows the GettingStartedGuide to build the library first.

The build instructions:

```

bzr branch http://benlau.e-fever.org/projects/bzr/GQRCodeReader GQRCodeReader

cd GQRCodeReader
./autogen.sh 
glade-2 -w gqrcodereader.glade
make
./src/gqrcodereader

```