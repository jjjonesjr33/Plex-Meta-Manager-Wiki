| Name                                                  | Shell Command                      | Environmental<br>Variable | Allowed Values                                                        | Default Value                                           |
|:------------------------------------------------------|:-----------------------------------|:--------------------------|:----------------------------------------------------------------------|:--------------------------------------------------------|
| [Config](#config)                                     | `-c` or `--config`                 | `PMM_CONFIG`              | Path to YAML config file                                              | `config/config.yml` alongside<br>`plex_meta_manager.py` |
| [Time to Run](#time-to-run)                           | `-t` or `--time`                   | `PMM_TIME`                | comma-separated list of times to update each day<br>**Format:** HH:MM | `03:00`                                                 |
| [Run](#run)                                           | `-r` or `--run`                    | `PMM_RUN`                 | Run without the scheduler                                             | `False`                                                 |
| [Run Tests](#run-tests)                               | `-rt`, `--tests`, or `--run-tests` | `PMM_TEST`                | Run in debug mode with only collections that have `test: true`        | `False`                                                 |
| [Run Collections Only](#collections-only)             | `-co` or `--collections-only`      | `PMM_COLLECTIONS_ONLY`    | Process only collections during the run                               | `False`                                                 |
| [Run Libraries Only](#libraries-only)                 | `-lo` or `--libraries-only`        | `PMM_LIBRARIES_ONLY`      | Process everything but collections during the run                     | `False`                                                 |
| [Run Collections](#run-collections)                   | `-rc` or `--run-collections`       | `PMM_COLLECTIONS`         | comma-separated list of collection names to process                   | All Collections                                         |
| [Run Libraries](#run-libraries)                       | `-rl` or `--run-libraries`         | `PMM_LIBRARIES`           | comma-separated list of library names to process                      | All Libraries                                           |
| [Run Metadata Files](#run-metadata-files)             | `-rm` or `--run-metadata-files`    | `PMM_METADATA_FILES`      | comma-separated list of metadata file names to process                | All Metadata Files                                      |
| [Run Libraries First](#run-libraries-first)           | `-lf` or `--libraries-first`       | `PMM_LIBRARIES_FIRST`     | Run library operations first before collections during the run        | `False`                                                 |
| [Ignore Schedules](#ignore-schedules)                 | `-is` or `--ignore-schedules`      | `PMM_IGNORE_SCHEDULES`    | Ignore all schedules during the run except for range schedules        | `False`                                                 |
| [Delete Collections](#delete-collections)             | `-dc` or `--delete-collections`    | `PMM_DELETE_COLLECTIONS`  | Delete all collections in a Library before a run                      | `False`                                                 |
| [Resume Run](#resume-run)                             | `-re` or `--resume`                | `PMM_RESUME`              | Name of the Collection you want to resume the run at                  | ` `                                                     |
| [No Countdown](#no-countdown)                         | `-nc` or `--no-countdown`          | `PMM_NO_COUNTDOWN`        | Run without displaying the countdown                                  | `False`                                                 |
| [No Missing](#no-missing)                             | `-nm` or `--no-missing`            | `PMM_NO_MISSING`          | Run without any of the missing movie/show functions                   | `False`                                                 |
| [Read Only Config](#read-only-config)                 | `-ro` or `--read-only-config`      | `PMM_READ_ONLY_CONFIG`    | Run without writing to the config                                     | `False`                                                 |
| [Divider Character](#divider-character--screen-width) | `-d` or `--divider`                | `PMM_DIVIDER`             | Character that divides the sections                                   | `=`                                                     |
| [Screen Width](#divider-character--screen-width)      | `-w` or `--width`                  | `PMM_WIDTH`               | Integer between 90 and 300                                            | `100`                                                   |

* Environmental Variable values are used over Shell Command values 

### Config
To choose the location of the YAML config file use the `--config` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --config <path_to_config>
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --config <path_to_config>
```

</details>

### Time to Run
To choose the times when the script will run each day use a comma-separated list with the `--time` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --time 22:00,03:00
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --time 22:00,03:00
```

</details>

### Run
To just run the script without having it continuously run use the `--run` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --run
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --run
```

</details>

### Run Tests
To run the script in debug mode while only running collections that have `test: true` use the `--run-tests` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --run-tests
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --run-tests
```

</details>

### Collections Only
To have the script run only collections and not any library operations use the `--collections-only` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --collections-only
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --collections-only
```

</details>

### Libraries Only
To have the script run only library operations and not any collections use the `--libraries-only` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --libraries-only
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --libraries-only
```

</details>

### Run Collections
To have the script run only using the collections in the comma-separated list use the `--run-collections` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --run-collections "Harry Potter, Star Wars"
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --run-collections "Harry Potter, Star Wars"
```

</details>

### Run Libraries
To have the script run only the libraries in the comma-separated list use the `--run-libraries` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --run-libraries "TV Shows"
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --run-libraries "TV Shows"
```

</details>

### Run Metadata Files
To have the script run only the Metadata File Names in the comma-separated list use the `--run-metadata-files` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --run-metadata-files "Movies"
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --run-metadata-files "Movies"
```

</details>

* This works for all different metadata paths i.e. `git`, `url`, `file`, or `repo`.

### Run Libraries First
To have the script run library operations first before collections during the run use the `--libraries-first` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --libraries-first
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --libraries-first
```

</details>

### Ignore Schedules
To have the script ignore all schedules during the run except for range schedules use the `--ignore-schedules` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --ignore-schedules
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --ignore-schedules
```

</details>

### Delete Collections
To have the script delete all collections in a Library before a run use the `--delete-collections` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --delete-collections
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --delete-collections
```

</details>

### Resume Run
To have the script resume a run from a specific collection use the `--resume` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --resume "Star Wars"
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --resume "Star Wars"
```

</details>

### No Countdown 
To have the script run without displaying a countdown use the `--no-countdown` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --no-countdown
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --no-countdown
```

</details>

### No Missing 
To have the script run without any of the missing movie/show functions use the `--no-missing` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --no-missing
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --no-missing
```

</details>

### Read Only Config
To have the script run without writing to the config use the `--read-only-config` option.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --read-only-config
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --read-only-config
```

</details>


### Divider Character & Screen Width
To change the terminal output divider character or width use the `--divider` and `--width` options.

<details>
  <summary>Local</summary>

```shell
python plex_meta_manager.py --divider * --width 200
```

</details>
<details>
  <summary>Docker</summary>

```shell
docker run -it -v "X:\Media\Plex Meta Manager\config:/config:rw" meisnate12/plex-meta-manager --divider * --width 200
```

</details>
