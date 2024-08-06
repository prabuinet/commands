## sed

**remove spaces**<br>
`sed 's/[ ]*//'`

## sort

**sort integer files**<br>
sort -n

**sort integer files and trim spaces**<br>
sort -n < 32kint.txt | sed 's/[ ]*//' > sorted.txt

