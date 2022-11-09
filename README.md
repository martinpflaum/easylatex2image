# Another Latex Converter 2 Image
This is a simple converter from latex to pillow images. The main function is latex_to_image. The input packages_and_commands must include all packages and custom enviroments, custom commands. Just write it as normal latex. In packages_and_commands do not use \begin{document} just simple usepacke stuff and commands! The content argument is the content that should be visualized. This literally can be annything. We are using a real latexcompiler in the backend. out_file_name is a string or None if you don't want a file to bewritten. dpi is the resolution. Higher is better but with more storage. 


The output type is a pillow image so you can convert it to a numpy array with np.array(pillow_image) and then go from there. Also ofcourse you can safe it as png with pillow_image.save().

``` python
import easylatex2image
from easylatex2image import latex_to_image

packages_and_commands = r"""\usepackage[parfill]{parskip}
\usepackage[german]{varioref}
\usepackage{url}
\usepackage{amsmath} 
\usepackage{dcolumn}
\usepackage{tikz}
\usetikzlibrary{shapes,arrows}
\usetikzlibrary{intersections}
\usepackage[all,cmtip]{xy}
"""

content = r"""
\xymatrix{M \ar[d]_\kappa \ar[r]^f & A\\ K \ar[ur]_{f_K}}
"""
pillow_image = latex_to_image(packages_and_commands,content,"output.jpg",dpi=500,img_type="JPEG")
```

Also with the r before the string you can just pass the latex code as it is without \n or something like that.
# Installation 
You can install python code with ```pip install easylatex2image```.
The libary needs miktex (link: https://miktex.org) to be installed. If you have AVast installed miktex might not work. A possible solution would to
1. go to menu
2. go to settings.
3. go to execptions.
4. add pdflatex command as execption.
Avast also might ask you if you want to make an execptions if you reboot. 

also u might need to install 
conda install -c conda-forge poppler

Alternative Solution: Use Linux :)
