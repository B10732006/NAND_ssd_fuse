# NAND_ssd_fuse
Use the file system to simulate the operation of fuse in ssd

# Description of the project
This is a lab from the course of College of Artificial Intelligence, National Yang Ming Chiao Tung University.

The code was provided by PHISON and we have to implement the folling tasks.

• Complete basic write/read function

• Modify writing sequence A to sequence B

• Implement garbage collection

# Setup the environment and the pakage

Run the following command in ubuntu-20.04.4

    apt-cache search fuse
    sudo apt-get update
    sudo apt-get install fuse3
    sudo apt-get install libfuse3-dev
    sudo apt-get install pkg-config
    sudo apt-get install libopencv-dev


# Compile the c code and create the file

First we have to change the NAND_LOCATION in the 18th line of ssd_fuse_header.h

Line 18:  #define NAND_LOCATION  **"(Add the path to where you  put your project)"** 

Then we have to compile the c file

    ./make_ssd

Create dir mount at /tmp/ssd

    mkdir /tmp/ssd
    ./ssd_fuse -d /tmp/ssd

# 8 NAND will be create and simulate the behavior of ssd using the file system, and the following command can interacte with the NAND

we can use ssd_fuse_dut to interact with the NAND.

We can write the data into the NAND through the following command

./ssd_fuse_dut /tmp/ssd/ssd_file w **LENTH_OF_DATA** **OFFSET_OF_DATA**   

    ./ssd_fuse_dut /tmp/ssd/ssd_file w 200 100

Read the data into the NAND through the following command

./ssd_fuse_dut /tmp/ssd/ssd_file r **LENTH_OF_DATA** **OFFSET_OF_DATA**   

    ./ssd_fuse_dut /tmp/ssd/ssd_file r 200 100

Check the logical address size

    ./ssd_fuse_dut /tmp/ssd/ssd_file l

Check the physical address size

    ./ssd_fuse_dut /tmp/ssd/ssd_file p





