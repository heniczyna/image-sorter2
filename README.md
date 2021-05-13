* Tested with Python 3.7.9,
* venv `venv379_image_sorter` (check possible venv with `workon` command - it comes from `virtualenvwrapper`)
* `pip install -r requirements.txt`
* changes in `image-sorter2_script.py`:
  * `input_folder = 'images/'`
  * `labels = ["human", "not_human"]` - it automatically creates corresponding folders in `input_folder`
  * `copy_or_move = 'move'` - moves original images to corresponding folders, does not create a copy
    * I have tested also `copy_or_move = 'copy'` however be careful with required `df_path = 'sort.txt'` (this file can not exist physically before running script, otherwise it causes errors, just specify the name and that is all)
  * `file_extensions = ['.png', '.raw']` - script returns some warnings when reads `.raw` files however moving to corresponding folders still work (when `.png` and `.raw` files have the same same, the script reads in the way as follows: `1.raw`->`1.png`, `2.raw`->`2.png` (or `.png` file first, but does not matter), and you need to remember to hit class name twice to move both of them to corresponding folder (one for `.raw` and one for `.png`)

# image-sorter2
One-click image sorting/labelling script. Copies or moves images from a folder into subfolders.

<img width="700" alt="pic_github_readme" src="https://user-images.githubusercontent.com/16193553/53246066-89bfd680-36a7-11e9-9eaf-9adee0b8efa1.png">


This script is intended to be a help for users sorting a set of mixed images into folders differentiated by classes - e.g. cats image folder, dog images folder, bikes images folder a.s.o. The script launches a GUI which displays one image after the other and lets the user give different labels, corresponding to different folders, from a list provided as input by the user. In contrast to original version, version 2 allows for relabelling and keeping track of the labels. Provides also short-cuts - press "1" to put into "label 1", press "2" to put into "label 2" a.s.o.

## Usage:

run 'pip install -r requirements.txt' to install dependencies. 

then

run 'python sort_folder_vers2.py' or copy the script in a jupyter notebook and run then. You need also to provide your specific input in the file-header (source folder, labels, 'copy' or 'move' mode, path to tracker file, desired file extensions (.jpg, .png, ...), resize keeping original aspect ratio or display original). Read the header in the .py-script, follow the discriptions and make the necessary changes to run it on your machine.

## Other useful scripts:
A list of other image labelling/sorting script that might be helpful

https://github.com/NaturalIntelligence/imglab

https://github.com/opencv/cvat

https://github.com/Cartucho/OpenLabeling

https://github.com/JNingWei/Image_Algorithm_Toolbox

https://play.google.com/store/apps/details?id=co.slidebox

### Authors:
original Author: Christian Baumgartner (c.baumgartner@imperial.ac.uk),
see here original "image-sorter" code: https://github.com/baumgach/image-sorter

changes, version 2: Nestor Arsenov (nestorarsenov_AT_gmail_DOT_com), created at London Center for Nanotechnology with project funding provided by The Foundation for Innovative New Diagnostics (FIND)

Date: 22. Feb 2019
