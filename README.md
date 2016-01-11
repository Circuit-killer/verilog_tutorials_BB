verilog tutorials for iCE40HX8K Breakout Board

Install IceStorm: http://www.clifford.at/icestorm/

Install necessary tools:

    sudo apt-get install git cmake 

Clone the repository:

    git clone https://github.com/peepo/verilog_tutorials_BB

Build one of the examples:

    cd project
    make
    make upload

NB make upload uses -S to program SRAM so please remove J7 jumper and rotate 2xJ6 jumpers

Project

0	LED
00	LED with +out
000	switch tbc
1						button
2	Synchronous Logic Tutorial		LED blink	1Hz
3	PWM - No DCM?				LEDs fade	4x, 6x with clk_50 from divider
4	PWM2					LEDs animate 	8 LEDs fade in and out together ~1.5hz timing seems anomalous
5	PWM3					LEDs wave	8 LEDs fade in and out in sequence
6	_tb					testbed and	basic and 
7	_tb2					testbed clk	pwm for a couple of values
8	ext button				ext button	6,800Ω connects + to input and switch, negative to other end switch
9	metastability				ext button	with debounce
10	servo					PWM		smallest servo P2 red-1 brown-2 orange-3
	Hello World				AVR		rely on AVR microcontroller in mojo, PIC is competitor
	--					--		mimas, XuLA2 have PIC18F14K50, 
	SPI					--		logipi may not have microcontroller? has spansion flash
	LogiCore				RAM		no project...
17	Mimas-Timing				100Mhz		builds with expected timing errors : odd that when run @50Mhz no errors?
18	Mimas-Timing_pipeline			100Mhz		builds with no timing errors due to pipeline
19	Finite State Machine			LEDs 2x		left_PWM & right_PWM, maybe also 5x states, ie forward....
	Memory mapping				AVR		ibid
	SDRAM					N/A		MimasV2	possibly or XuLA2 SDRAM before writing to SDcard
	Embedded processor			N/A		skipping for moment.

---

please send comments, and report bugs to the current maintainer: Jonathan Chetwynd

jay@peepo.com

created in conjunction with these excellent resources:

https://embeddedmicro.com/tutorials/mojo/creating-a-project

https://nandland.com/verilog/tutorials/tutorial-introduction-to-verilog-for-beginners.html

---

when cmake is implemented:

Build one of the examples:

    cd verilog_tutorials_BB/build
    cmake ..
    cd project_0/
    make
    ./LED

Build all examples (takes a while):

    cd verilog_tutorials_BB/build
    cmake ..
    make
