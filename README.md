
1. Add "src-git VincentGijsen git://github.com/VincentGijsen/OpenWRT-ShairPort.git;master" to feeds.conf
2. Remove the jlars feed (to avoid ShairPort conflict)
3. scripts/feeds update -a
4. scripts/feeds install -a

More cleanup for smaller footprint

