# MOBI2.2_local
Local run directories for UVic climate model with MOBI2.2.

### Prerequisites
You need the base code of the model installed. Here you need [UVic2.9](https://github.com/OSU-CEOAS-Schmittner/UVic2.9) updates level [09 (MOBI2.2)](https://github.com/OSU-CEOAS-Schmittner/UVic2.9/releases/tag/v2.9.09).

### Installing
1. Clone the repository:
```
git clone https://github.com/andreasschmittner/MOBI2.2_local.git
```
2. Goto your run directory:
```
cd o2_n_fe_si_ca_caco3_c13_n15_c14
```
2. Copy the data directory from [MOBI2.1](https://github.com/andreasschmittner/MOBI2.1_local.git) and add the file from this data directory to it.
```
cp -r PATH/MOBI2.1_local/data .
cp ../data/* data/.
```
3. Modify the `run.q` script so that the path reflects your current working directory. This is the file that you submit to the job scheduler. It works on OSU's Humboldt cluster. If you work on a different computer you may have to adjust it. I also like to rename the script so that you can distinguish it from other runs you have going on.

4. Compile code
```
mk e
```
5. If compilation was successful you should see the executable (UVic_ESCM) and you can start your simulation by submitting the run script.
```
qsub run.q
```

