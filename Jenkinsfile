
try {
	node('windows-slave-2') {
		try {
			checkout scm
			copyArtifacts filter: 'libnonlayeredtidytrees.zip', projectName: '/tidyTrees/master'
bat '''

wget https://github.com/bauing-schmidt/lua-windows/archive/refs/tags/v5.4.4.zip
unzip -o v5.4.4.zip
mv lua-windows-5.4.4\\local .
rm -rf lua-windows-5.4.4

unzip -o libnonlayeredtidytrees.zip
mv libnonlayeredtidytrees.dll local\\lib
mv non-layered-tidy-trees.h local\\include

cd src
make jenkins
cd ..
mkdir -p local\\share\\lua\\5.4
mkdir -p local\\lib\\lua\\5.4
cp src\\liblua-non-layered-tidy-trees.lua local\\share\lua\\5.4\\
cp src\\libluanonlayeredtidytrees.dll local\\lib\lua\\5.4\\

zip -r libluanonlayeredtidytrees.zip local
'''
		} finally {
			archiveArtifacts artifacts: 'src/libluanonlayeredtidytrees.zip'
			cleanWs()
		}
	}
} catch(e) {
	throw e
}
