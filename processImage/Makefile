SHELL=/bin/bash
xOffset = 2
yOffset = 4
imageWidth = 250
imageHeight = 336 
xWidth =$(shell echo $$((250 * 2 + $(xOffset) * 2))) 
yWidth = $(shell expr $(imageHeight) \* 2 + $(yOffset) \* 2) 
type = jpg
cropParams = $(xWidth)x$(yWidth)+$(xOffset)+$(yOffset)
#cropParams = 504x680+2+4 
montage:
	 montage fat_large_L.jpg fat_large_R.jpg fat_large_1_L.jpg fat_large_1_R.jpg -geometry +$(xOffset)+$(yOffset) test.jpg
	 convert test.jpg -crop $(cropParams) -set filename:f '%t' '%[filename:f].png'
	 open test.png

test: 
	y=" $(cropParams)"; \ 
	echo $y
	 FOO_NO_WHITESPACE="$(echo -e "${y}" | tr -d '[:space:]')"; \ 
	 echo $FOO_NO_WHITESPACE 
