# Note

存放一些可能用得上的东西，类似 cheat sheets。

## Latex

编译 tex 文件

**dos**

```bat
@for %%a in (*.tex) do (
	latexmk -pdf -xelatex -file-line-error -halt-on-error -interaction=nonstopmode -synctex=1 "%%a" 
	latexmk -c
	del *.xdv *.gz *.bbl *.xml *.thm
	powershell ./"%%~na.pdf"
)
```

**unix**

```bash
for a in *.tex; do
	echo $a
	latexmk -pdf -xelatex -file-line-error -halt-on-error -interaction=nonstopmode -synctex=1 "$a" 
	latexmk -c
	rm *.xdv *.gz *.bbl *.xml *.thm
done
```

