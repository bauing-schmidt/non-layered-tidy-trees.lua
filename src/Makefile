
linux:
	cc -O2 -std=gnu17 -fPIC -Wall -shared -o libluanonlayeredtidytrees.so liblua-non-layered-tidy-trees.c -llua -lnonlayeredtidytrees
	
macos:
	cc -O2 -std=c17 -fPIC -Wall -dynamiclib -I/usr/local/include/ -o libluanonlayeredtidytrees.dylib liblua-non-layered-tidy-trees.c -L/usr/local/lib/ -llua -lnonlayeredtidytrees

mingw:
	gcc -O2 -fPIC -Wall -I/usr/local/include/ -s -shared -o libluanonlayeredtidytrees.dll liblua-non-layered-tidy-trees.c -L/usr/local/lib/ -llua -lnonlayeredtidytrees

jenkins:
	gcc -O2 -fPIC -Wall -I../../lua-5.4.6/include/ -s -shared -o libluanonlayeredtidytrees.dll liblua-non-layered-tidy-trees.c -L../../lua-5.4.6/lib/ -llua54 -lnonlayeredtidytrees

test:
	gcc -I/usr/local/include/ -o libluanonlayeredtidytrees.dll liblua-non-layered-tidy-trees.c -L/usr/local/lib/ -llua -lnonlayeredtidytrees
	
install:
	mkdir -p /usr/local/lib/lua/5.4/	# just for ensuring that the dest dir exists
	mkdir -p /usr/local/share/lua/5.4/	# just for ensuring that the dest dir exists
	mv libluanonlayeredtidytrees.so /usr/local/lib/lua/5.4/
	cp non-layered-tidy-trees.lua /usr/local/share/lua/5.4/

install-macos:
	mkdir -p /usr/local/lib/lua/5.4/	# just for ensuring that the dest dir exists
	mkdir -p /usr/local/share/lua/5.4/	# just for ensuring that the dest dir exists
	mv libluanonlayeredtidytrees.dylib /usr/local/lib/lua/5.4/
	cp non-layered-tidy-trees.lua /usr/local/share/lua/5.4/

mingw-install:
	mkdir -p /usr/local/lib/lua/5.4/	# just for ensuring that the dest dir exists
	mkdir -p /usr/local/share/lua/5.4/	# just for ensuring that the dest dir exists
	mv libluanonlayeredtidytrees.dll /usr/local/lib/lua/5.4/
	cp non-layered-tidy-trees.lua /usr/local/share/lua/5.4/

