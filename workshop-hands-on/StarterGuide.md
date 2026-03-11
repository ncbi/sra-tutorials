# SRA Toolkit Tutorial Guide

This guide will walk you through **installing, configuring, and using the SRA Toolkit** .  

For more information, you can always visit the [NCBI SRA-Tools GitHub wiki](https://github.com/ncbi/sra-tools/wiki) for more comprehensive information.

---

## 1. Download and Install the SRA Toolkit

### Windows

1. Download the latest Windows binary available on the [SRA Toolkit Releases](https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit) page. For example,  `sratoolkit.current-win64.zip`.
 
2. Extract the `.zip` file to an accessible location, for example onto your `Desktop`.

3. Open your Windows Command Prompt (`Win + R`, type `cmd`).

4. Navigate (using the `cd` command) to the location of your toolkit folder. Specifically, into the 

    ```cmd
	cd Desktop
    cd sratoolkit.current-win64
    cd bin
    ```    

5. Great! Move to the next section, "2. Configure the SRA Toolkit".



### macOS and Linux (using Homebrew)

Homebrew (available at [brew.sh](https://brew.sh/)) is a utility that installs [from a massive list of software packages](https://formulae.brew.sh/formula/"). Each installation goes to their own directory.

This is a very easy way to install the SRA Toolkit, but the downside is that Homebrew takes a few weeks to update its packages, so if you want the most up-to-date version of `sratoolkit` you should install directly from the SRA Toolkit Github repository.

1. Open your Terminal — open your search menu (`⌘ + Space` on Mac, `Win` on Linux) and then type "Terminal". In the Terminal window, install Homebrew, 

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Install `sratoolkit`.

```bash
brew install sratoolkit
```

3. That's it! You can move onto the next section, "2. Configure the SRA Toolkit".



### macOS and Linux (direct from NCBI)

1. Open your Terminal — open your search menu (`⌘ + Space` on Mac, `Win` on Linux) and then type "Terminal".

2. In the Terminal window, download the latest binary using the command that corresponds to your operating system.

    ```bash
    # macOS
    curl --output sratoolkit.tar.gz \
    https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-mac64.tar.gz
    
    # Ubuntu
    wget --output-document sratoolkit.tar.gz \
    https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-ubuntu64.tar.gz
    
    # AlmaLinux
    wget --output-document sratoolkit.tar.gz \
    https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-alma_linux64.tar.gz
    ```

3. Extract the file using the following command.

    ```bash
    tar -vxzf sratoolkit.tar.gz
    ```    

4. Add `bin` to your `PATH`:

    ```bash
    export PATH=$PWD/sratoolkit.<version>/bin:$PATH
    ```

5. That's it! You can move onto the next section, "2. Configure the SRA Toolkit".

---

## 2. Configure the SRA Toolkit

1. Run the interactive configuration tool to open the “SRA Configuration" menu.

```bash
vdb-config -i
```

2. Use `Tab` to navigate the options, and `Enter` to select.

3. In the "MAIN" menu tab, toggle “Enable Remote Access".

4. In the "CACHE" menu tab, make sure that “Enable Local File Caching” is toggled.

5. Select “Choose” under the “Location of user-repository” section. You **must** select an empty directory, so create one if you do not have one.

6. Save your changes by selecting the "Save" option. Then select the "Exit" option.

7. Move on to the next section.

---

## 3. Test Your Installation

Run a quick check:

```bash
fastq-dump --stdout -X 2 SRR390728
```

If you see 2 reads in FASTQ format, your installation is working!

---

## 4. Using SRA Toolkit

1.  Use the following `vdb-dump` to check accession info, including how large the file is.

```bash
vdb-dump SRR1553607 --info
```

2. Use `prefetch` to download the run file of the accession. This saves `.sralite` or `.sra` files in your repository directory.

```bash
prefetch SRR1553607
```

3. Use `fasterq-dump` to convert the accession into FASTQ files. This example will generate `SRR1553607_1.fastq` and `SRR1553607_2.fastq`.

```bash
fasterq-dump SRR1553607
```

4. Please note storage considerations! The SRA Toolkit needs **~18× the size of the accession** during conversion using `fasterq-dump`. For example,  a 500MB `.sra` file would need  ~9GB free disk space in order to generate temporary files, and the final FASTQ files. You can check free space with:

```bash
df -h
```

---

## 5. Getting Help

Each tool has built-in help using the `--help` or `h` option. For example, for `fasterq-dump` you could use the following options:

```bash
fasterq-dump --help
# or
fasterq-dump -h
```

