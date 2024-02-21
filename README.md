# jpath-issue-reproducer

Working:
```
JSONNET_PATH=$(pwd)/vendor1:$(pwd)/vendor2 jsonnet -e "(importstr 'lib1/shared1.txt')+(importstr 'lib2/shared2.txt')"

> "shared1shared2"
```

Not working:
```
jsonnet --jpath $(pwd)/vendor1:$(pwd)/vendor2 -e "(importstr 'lib1/shared1.txt')+(importstr 'lib2/shared2.txt')"

> RUNTIME ERROR: couldn't open import "lib1/shared1.txt": no match locally or in the Jsonnet library paths
	<cmdline>:1:2-30	$
	During evaluation	
```
