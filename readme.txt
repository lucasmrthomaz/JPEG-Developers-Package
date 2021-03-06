JPEG Developers Package 02/18/2014
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This package contains source code for special JPEG decompression and 
recompression routines, which may help developers as a framework in 
building their own JPEG recompression applications or as a base for 
other JPEG related projects. These routines were designed from scratch 
and are also used in packJPG now. Instructions on how to begin your own 
JPEG recompression algorithm (for anyone interested) are included in the 
source code.


BSD License
~~~~~~~~~~~

All programs in this package are free software. Except for lpaqJPEGtest, 
which uses code by Matt Mahoney and is released under the terms of the 
GPL, you may use any binaries and software included in this package 
under the terms of the BSD. Read more about the terms of the BSD here: 
http://www.linfo.org/bsdlicense.html. 


Included Programs
~~~~~~~~~~~~~~~~~

A short explanations for each of the included programs is given in the 
following paragraphs. For more detailed information please refer to the 
programs integrated help function or the source code. In any program you 
can view the integrated help by just running it from the command line 
without any parameters. 

uncmpJPG v2.4a
~~~~~~~~~~~~~~
uncmpJPG is the name of the special core JPEG codec used in packJPG. 
Compared to other JPEG codecs the main difference is that this codec 
performs decompression and recompression without introducing any further 
loss - a JPEG file that goes in it is bytewise identical to the JPEG 
file that goes out. As such, this codec is well suited to be used in 
lossless JPEG recompression projects. There are some rare cases in which 
a JPEG file can't be processed losslessly. In these cases uncmpJPG will 
display a error message. 

uncmpJPG accepts JPEG and UJG (Uncompressed JpeG) files as input - JPEG 
are converted to UJG and vice versa. An UJG file consists of all 
information needed to losslessly reconstruct the original JPEG file. 
Contained are JFIF file header, decompressed DCT coefficients and, if 
needed, some special file reconstruction information. 

lpaqJPGtest v2.4 alpha 1
~~~~~~~~~~~~~~~~~~~~~~~~
lpaqJPEGtest is a sample JPEG recompression application build on top of 
uncmpJPG using a slightly modified version of Matt Mahoney's and 
Alexander Ratushnyak's lpaq1v2 for compression and decompression. It's 
here as an example on how to modify uncmpJPG to do recompression to a 
JPEG file. Other than uncmpJPG or packJPG, lpaqJPGtest currently only 
accepts one file per run. 

Please note: lpaqJPGtest is in alpha stage and by no means intended to 
be used to archive your images. I've tested it without any problems, but 
still, it might crash and/or compress files to a state where they can't 
be decompressed. There are better, faster, more reliable, and more 
comfortable alternatives around (why not use packJPG?). 

tranDCT v0.9b
~~~~~~~~~~~~~
tranDCT is a tool for examining dependencies between DCT coefficients in 
an image. It should be useful not only for JPEG but basically for all 
DCT transformation based 2D compression schemes. tranDCT accepts input 
files of type PGM (Portable GrayMap), DCT (DCT coefficients with 
header), and TDS (TranDct Script) and writes PGM, DCT, RWC (RaW 
Coefficients), or CSV (Comma Separated Values) as output. By default it 
converts PGM to DCT and vice versa. Be warned though, as this is not 
fully lossless due to roundoff errors in the IDCT/FDCT. 

Transformed DCT coeffients from a PGM file can be visualized in various 
formats. Please refer to the integrated help or to the included sample 
files for more information. If a TDS file and one or more PGM files are 
given as input, the output is an Excel/OpenOffice.Org compatible CSV 
file containing coefficient data for analysis. For the structure of a 
TDS file please refer to the included sample TDS file. 

jpeginfo v1.0b
~~~~~~~~~~~~~~
jpeginfo processes one or more JPEG files and writes a single 
Excel/OpenOffice compatible CSV (Comma Separated Values) called 
"JPEGinfo.csv". The resulting table contains, for each image, basic and 
advanced information such as estimated quality of the image, type of 
color subsampling or JPEG coding mode. 

makepgm v2.0a
~~~~~~~~~~~~~
makepgm converts a given (binary) file to a PGM image, viewable in most 
common graphic viewing programs. It is especially useful for 
visualization of f.e. uncmpJPGs output. Various options for setting the 
width/height of the resulting image and format of the input data are 
included. By default, makepgm uses a heuristic matching algorithm to 
find the width/height that matches best with the given input data. 

hcheck v2.0
~~~~~~~~~~~
hcheck estimates the 0th to 4th order entropy of any given input file. 
Entropy is a measure for the theoretically possible compression on a 
given stream of data, for more info please refer to 
http://en.wikipedia.org/wiki/Entropy_(information_theory). hcheck 
displays all relevant information on screen, but it it can also write a 
Excel/OpenOffice.Org compatible CSV file. 

extrjpg v0.1
~~~~~~~~~~~~
extrjpg scans one or more input files for embedded JPEG files and 
extracts all found images to the disk. Such embedded images are very 
often, for example, contained in PDF files. Please note that extrJPG is 
still in an early stage and might, in some rare cases, dump non-JPEG 
files as well. Large file support (LFS) for files larger than 4GB is 
disabled by default but can be enabled by defining "LFS" in the source 
code. 

modjpg v0.9
~~~~~~~~~~~
modJPG works in a similar way to JPEGinfo in that it can process a 
number of JPEG files and output some basic and advanced information to a 
CSV file called ‘JPEGinfo.csv’. Additionally there is some 
functionality to modify existing JPEG files without introducing 
unnecessary loss. 

Modification functionality in modJPG includes the following:
o Discard meta information
o Discard garbage data
o Strip restart markers
o Requantize all coefficients with a factor of your choice
o Modify quantization tables

modJPG was coded from existing packJPG code on request by Prof. Dr. 
Seelmann of HTW Aalen University. You may freely use it and the included 
source code under the terms of the BSD. 


Acknowledgements
~~~~~~~~~~~~~~~~

Prof. Dr. Gerhard Seelmann from Hochschule Aalen supported my research 
in JPEG compression with his extensive knowledge in the field of data 
compression. Without his advice, this package would not be possible. 

lpaqJPGtest contains slightly modified arithmetic compression routines 
originally written by Matt Mahoney and further improved by Alexander 
Ratushnyak known as "LPAQ1 ver 2". LPAQ1 belongs to the excellent series 
of PAQ archivers by Matt Mahoney and others. Its unaltered source code 
and corresponding windows executables can be found here: 
http://www.cs.fit.edu/~mmahoney/compression/. 


Contact
~~~~~~~

The official developer blog for packJPG:
 http://packjpg.encode.ru/
 
For questions and bug reports:
 packjpg (at) matthiasstirner.com
 

____________________________________________________
JPEG Developers Package by Matthias Stirner, 01/2016 

