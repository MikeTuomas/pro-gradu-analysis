# Pro gradun aineiston käsittely ja analyysi
Tämä repo sisältää pro gradussani aineiston käsittelyyn ja analyysiin käytetyt tiedostot. 

``Datasetin luonti.ipynb`` sisältää AOSpan aineiston muokkauksen käsiteltävään muotoon ja siihen kyselyaineston yhdistämisen. 

``.jasp`` tiedostot sisältävät cronbachin alphan laskennat.

``Tilastoanalyysit.Rmd`` sisältää aineiston analyysit.


## Python notebooks usage
Create environment from the file, register it to ipykernel and open jupyterlab. It is assumed that Jupyterlab is installed in the base env of python.
```
conda env create -f environment.yml
conda activate dataset
python -m ipykernel install --user --name=dataset
conda deactivate
jupyter lab
```

### Modifying environment.yml

#### After changing the environment
1. Overwrite the environment.yml
``conda env export --name dataset > environment.yml``
2. Commit changes
#### Applying changes in environment
1. Deactivate the environment you are in by typing in the terminal: conda deactivate (this step is necessary only if you are currently in the environment you want to update)
2. Then type ``conda env update -f environment.yml``
3. Reactivate the environment by ``conda activate <environment_name>``
### How this env was created
```
conda create -n dataset python=3.10 pandas ipykernel
conda activate dataset
python -m ipykernel install --user --name=dataset
conda env export --name dataset > environment.yml
```
