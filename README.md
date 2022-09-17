# Image Cartopartie Claix 2022-09-10

## Bigmap

1. http://bigmap.osmz.ru/bigmap.php?zoom=13&xmin=4223&ymin=2942&xmax=4226&ymax=2944&tiles=mapnik
2. http://bigmap.osmz.ru/bigmap.php?xmin=8446&xmax=8453&ymin=5884&ymax=5889&zoom=14&scale=256&tiles=mapnik
3. http://bigmap.osmz.ru/bigmap.php?xmin=16895&xmax=16902&ymin=11768&ymax=11775&zoom=15&scale=256&tiles=mapnik
4. http://bigmap.osmz.ru/bigmap.php?xmin=33796&xmax=33804&ymin=23537&ymax=23547&zoom=16&scale=256&tiles=mapnik
5. http://bigmap.osmz.ru/bigmap.php?xmin=67596&xmax=67609&ymin=47089&ymax=47095&zoom=17&scale=256&tiles=mapnik
6. http://bigmap.osmz.ru/bigmap.php?xmin=135194&xmax=135200&ymin=94178&ymax=94191&zoom=18&scale=256&tiles=mapnik
7. http://bigmap.osmz.ru/bigmap.php?xmin=135201&xmax=135207&ymin=94178&ymax=94191&zoom=18&scale=256&tiles=mapnik
8. http://bigmap.osmz.ru/bigmap.php?xmin=135208&xmax=135214&ymin=94178&ymax=94191&zoom=18&scale=256&tiles=mapnik
9. http://bigmap.osmz.ru/bigmap.php?xmin=135215&xmax=135221&ymin=94178&ymax=94191&zoom=18&scale=256&tiles=mapnik
10. http://bigmap.osmz.ru/bigmap.php?xmin=67598&xmax=67607&ymin=47075&ymax=47084&zoom=17&scale=256&tiles=mapnik
11. http://bigmap.osmz.ru/bigmap.php?xmin=135196&xmax=135205&ymin=94150&ymax=94159&zoom=18&scale=256&tiles=mapnik
12. http://bigmap.osmz.ru/bigmap.php?xmin=135206&xmax=135215&ymin=94150&ymax=94159&zoom=18&scale=256&tiles=mapnik
13. http://bigmap.osmz.ru/bigmap.php?xmin=135206&xmax=135215&ymin=94160&ymax=94169&zoom=18&scale=256&tiles=mapnik
14. http://bigmap.osmz.ru/bigmap.php?xmin=135196&xmax=135205&ymin=94160&ymax=94169&zoom=18&scale=256&tiles=mapnik
15. http://bigmap.osmz.ru/bigmap.php?xmin=67596&xmax=67605&ymin=47084&ymax=47093&zoom=17&scale=256&tiles=mapnik
16. http://bigmap.osmz.ru/bigmap.php?xmin=67603&xmax=67612&ymin=47084&ymax=47093&zoom=17&scale=256&tiles=mapnik
17. http://bigmap.osmz.ru/bigmap.php?xmin=135196&xmax=135205&ymin=94172&ymax=94181&zoom=18&scale=256&tiles=mapnik
18. http://bigmap.osmz.ru/bigmap.php?xmin=270401&xmax=270410&ymin=188348&ymax=188357&zoom=19&scale=256&tiles=mapnik
19. http://bigmap.osmz.ru/bigmap.php?xmin=270430&xmax=270439&ymin=188349&ymax=188358&zoom=19&scale=256&tiles=mapnik
20. http://bigmap.osmz.ru/bigmap.php?xmin=270403&xmax=270412&ymin=188365&ymax=188374&zoom=19&scale=256&tiles=mapnik
21. http://bigmap.osmz.ru/bigmap.php?xmin=270390&xmax=270399&ymin=188371&ymax=188380&zoom=19&scale=256&tiles=mapnik
22. http://bigmap.osmz.ru/bigmap.php?xmin=270391&xmax=270400&ymin=188360&ymax=188369&zoom=19&scale=256&tiles=mapnik
23. http://bigmap.osmz.ru/bigmap.php?xmin=270393&xmax=270402&ymin=188351&ymax=188360&zoom=19&scale=256&tiles=mapnik
24. http://bigmap.osmz.ru/bigmap.php?xmin=135199&xmax=135208&ymin=94161&ymax=94170&zoom=18&scale=256&tiles=mapnik

## Add comment

```sh
mkdir tmp
magick convert -gravity NorthWest -pointsize 30 -undercolor yellow -annotate +10+10 "Avant" 01a.png tmp/01a.png
magick convert -gravity NorthWest -pointsize 30 -undercolor yellow -annotate +10+10 "Après" 01b.png tmp/01b.png
```

## Make gif

```sh
mkdir gif
magick convert -loop 0 -delay 200 tmp/01a.png tmp/01b.png gif/CartoClaix2022-01.gif
```

## With a loop
```sh
mkdir tmp
mkdir gif
for i in `seq -w 1 24`
do
    echo "Image ${i}..."
    magick convert -gravity NorthWest -pointsize 30 -undercolor yellow -annotate +10+10 "Avant" ${i}a.png tmp/${i}a.png
    magick convert -gravity NorthWest -pointsize 30 -undercolor yellow -annotate +10+10 "Après" ${i}b.png tmp/${i}b.png
    magick convert -loop 0 -delay 200 tmp/${i}a.png tmp/${i}b.png gif/CartoClaix2022-${i}.gif
done
```

## Crop images
```sh
magick convert 15a.png -crop 75x40%+600+1500 +repage 151a.png
magick convert 15b.png -crop 75x40%+600+1500 +repage 151b.png

magick convert 18a.png -crop 75x40%+200+600 +repage 181a.png
magick convert 18b.png -crop 75x40%+200+600 +repage 181b.png

magick convert 19a.png -crop 75x40%+0+0 +repage 191a.png
magick convert 19b.png -crop 75x40%+0+0 +repage 191b.png

magick convert 19a.png -crop 75x40%+200+600 +repage 192a.png
magick convert 19b.png -crop 75x40%+200+600 +repage 192b.png

for i in 151 181 191 192
# copy previous for bloc
```