#
# Copyright (C) 2023, Advanced Micro Devices, Inc. All rights reserved.
# SPDX-License-Identifier: X11
#


all:
	make data
	make -C Emulation-AIE all

run:
	make data
	make -C Emulation-AIE PFM_NAME=$(PFM_NAME) aie aiesim

aie:
	make -C Emulation-AIE aie

aiesim:
	make -C Emulation-AIE aiesim

aieviz:
	make -C Emulation-AIE aieviz

clean:
	rm data/*
	touch data/dummy.txt
	make -C Emulation-AIE clean
	rm -f vitis_analyzer*

data:
	cd ../Utils && ./GenerateStreams cint16 64 8 2 256 4 Dirac ../DualStreamSSR/data/PhaseIn

.PHONY: all clean aie aiesim aieviz data
