.PHONY: pdf booklet run clean

pdf: build/wave.pdf

booklet: build/wave-4x2-booklet.pdf

run: build/wave.pdf
	evince build/wave.pdf

build/wave.pdf: metadata.md wave.md build
	pandoc metadata.md wave.md -o build/wave.pdf

build/wave-booklet.pdf: build/wave.pdf
	pdftk A=build/wave.pdf cat A7south A6south A5south A4south A8 A1 A2 A3 output build/wave-booklet.pdf

build/wave-4x2-booklet.pdf: build/wave-booklet.pdf
	pdflatex -output-dir=build -jobname wave-4x2-booklet.pdf booklet.tex

build:
	mkdir -p build

clean:
	rm -rf build
