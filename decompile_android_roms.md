## DECOMPILE SYSTEM.NEW.DAT.BR  
1-win: brotli.exe --decompress --in system.new.dat.br --out system.new.dat  
2-win: sdat2img.py system.transfer.list system.new.dat system.new.img  
3-lin: mkdir system  
4-lin: sudo mount -t ext4 -o loop system.new.img system  
  
## DECOMPILE SYSTEM_EXT.NEW.DAT.BR  
1-win: brotli.exe --decompress --in system_ext.new.dat.br --out system_ext.new.dat  
2-win: sdat2img.py system_ext.transfer.list system_ext.new.dat system_ext.new.img  
3-lin: mkdir system  
4-lin: sudo mount -t ext4 -o loop system_ext.new.img system_ext  
  
## DECOMPILE VENDOR.NEW.DAT.BR  
1-win: brotli.exe --decompress --in vendor.new.dat.br --out vendor.new.dat  
2-win: sdat2img.py vendor.transfer.list vendor.new.dat vendor.new.img  
3-lin: mkdir vendor  
4-lin: sudo mount -t ext4 -o loop vendor.new.img vendor  
  
## DECOMPILE PRODUCT.NEW.DAT.BR  
1-win: brotli.exe --decompress --in product.new.dat.br --out product.new.dat  
2-win: sdat2img.py product.transfer.list product.new.dat product.new.img  
3-lin: mkdir product  
4-lin: sudo mount -t ext4 -o loop product.new.img product  
