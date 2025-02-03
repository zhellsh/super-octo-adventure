```zsh
./yoot_1.sh
```
```zsh
cd music
```
```zsh
for file in *.mp3; do mv -- "$file" "${file// /_}"
```
```zsh
for file in $(find -name "*.mp3" -type f); mv $file $(echo $file | sed "s/_\[.*\]//g")
```
```zsh
for file in *.mp3; mkdir $(echo $(ffmpeg -i $file 2> >(grep "album")) | sed 's/album : //g' | tr '\ ' '_')
```
```zsh
for file in *.mp3; mv $file $(echo $(ffmpeg -i $file 2> >(grep "album")) | sed 's/album : //g' | tr '\ ' '_')
```
```zsh
../yoot_2.sh
```
