# make_hw

Homework dedicated to 'make' and autotools

## Usage

### Getting started

1) Clone the repository.
    ```git clone https://github.com/yur4sh/make_hw.git```
2) Go to repo directory.
    ```cd make_hw```

### Configure

1) Generate staging autotools files.
    ```autoreconf -vi```

2) Configure and generate the Makefile.
    ```./configure```

### Build and install

1) Build the project and install locally withing the repository.
    ```make```

2) Install the program into system.
    ```sudo make install```

3) Check if installed successfully.
    ```ls -l /usr/local/bin/makehw```
    ```ls -l /usr/local/include/makehw```

4) Clean local build artifacts.
    ```make clean```

5) Clean and uninstall the program.
    ```sudo make clean-all```
