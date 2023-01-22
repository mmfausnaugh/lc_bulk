# TESS Transients: light curves under version control

Data are saved under version control by an application called [DVC (Data Version Control)](https://dvc.org/). DVC uses metadata files in this git repository to track different versions of the light curves. The calibration models are stored on a server at MIT, which DVC pulls with https GET requests.

To retrieve the data, first install DVC using the directions on the [DVC](https://dvc.org/) website. You can use the website's downloadable script, or you can use conda, pip, or homebrew on macOS.

Then clone this repository and run the following command:

```
dvc pull
```

to retrieve all of the data. Alternatively, you can get one sector at a time with, e.g., `dvc pull s58.tgz`.

Old versions of the data can be retrieved based on the history of the `s??.tgz.dvc` files. You can inspect the history with `git log`, and use  commands long the lines of 
```
git checkout <hash> s??.tgz.dvc
dvc pull s??.tgz
```
This will pull whatever version of the tarball is pointed to in the current version of the `.dvc` file (i.e., the checked out version of the `.dvc` file).

To unpack the tarball, run
```
tar -xvzf s??.tgz
```
