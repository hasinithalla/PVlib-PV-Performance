

CONTENTS
S.No. TITLE P.No.
1 Introduction 1
1.1 Introduction 1
1.2 Physics of solar cell 1
1.3 Solar Power technologies 2
1.4 Photo voltaic systems 3
1.5 Pvlib Python 6
1.6 Orientation of report 8
2 Mathematical modelling of PV system 9
2.1 Introduction 9 2.2 Single diode equivalent circuit model 9 2.3 De Soto “Five-Parameter” Module Model 11
2.4 PVsyst Module Model 12
2.5 The Lambert W method 14
2.6 Solar Cell I-V Characteristic Curve 14
2.7. Conclusion 16
3 Generating IV curves 17
3.1 Introduction 17
3.2 Pvlib Python 17
3.3 Pvlib concept 18
3.4 Using pvlib for python 19
3.5 Installing pvlib 20
3.6 Input parameters 20
3.7 Generating I-V curves 21
3.8 Outputs 24
3.9 Conclusion 25
4 Python vs Matlab 26
4.1 Introduction 26
4.2 Advantages of Matlab 27 4.3 Problems of Matlab 27
4.4 Advantages of Python ` 28
4.5 Pvlib Python vs Pvlib Matlab 29 4.6 Conclusion 30
Case study 1: Effect of Irradiance 31 Case study 2: Effect of temperature 33
5 Conclusion 30
6 References
VII
1
CHAPTER 1
INTRODUCTION
1.1. Introduction
Nowadays energy shortage is worldwide concern issue. Increased utilization of energy and global pollution awareness has made the renewable energy as a promising energy source. Due to increasing of energy demand in every year in the world, renewable energy can be an alternative option for improving this situation. Renewable energy is a great solution to solve these phenomena. Among renewable energy, solar energy is emerging as one of the best energy solutions. Solar Energy is a pollution free renewable energy sources which attributes high durability and reliability. Among the solar technology, the photovoltaic array (PV) has been making a positive attention due to its capability of energy conversion without intermediate thermal process.
Globally, the integration of the photovoltaic (PV) system with the grid spreads progressively where the contribution of PV generation to the overall worldwide power generation is augmented. The principal advantages associated with photovoltaic arrays are that it consists of no moving parts. Do not produce any noise and maintenance costs are minimal. It is also a clean source of energy. Amount of energy produced by the sun is so large, that in one hour it can provide more than enough energy for human population in one year. PV system shows non-linear I-V and P-V characteristics which varies with different types of environmental and electrical parameters.
1.2. Physics of Solar cell
Solar photovoltaic is a kind of technology which generates direct current (DC) using semiconductors when they are illuminated by photons. Photovoltaic system made of different cells which convert sunlight into electricity. Solar cells are generally made of semiconductor materials which contain weekly bonded electrons occupying a band of energy called valence band. When an
2
energy is applied to a valence electron (greater than threshold energy), the bonds of valence electron are broken and electron is free to move to another energy band named conduction band. The band gap separates the free electrons from conduction band to valence band. Photons which are particle of lights supplied the energy to free the electrons.
Figure1.1: Concept of solar cell in terms of physics
Solar cell is one kind of device that is fabricated in a thin layer of semiconductor. Solar cell is a p-n junction that is made by crystalline material like Si, GaAs, Ge etc. The main principle of solar cell is photoelectric effect. A typical solar cell device converts light energy into electrical energy.
1.3. Solar power technologies
1.3.1. Concentrating solar power (CSP) technology
Concentrating Solar Power (CSP) technologies use mirrors to concentrate (focus) the sun's light energy and convert it into heat to create steam to drive a turbine that generates electrical power. CSP technology utilizes focused sunlight. CSP plants generate electric power by using mirrors to concentrate (focus) the sun's energy and convert it into high-temperature heat. That heat is then
3
channeled through a conventional generator. The plants consist of two parts: one that collects solar energy and converts it to heat, and another that converts the heat energy to electricity.
1.3.2. Solar photovoltaic technology
Solar cells, also called photovoltaic (PV) cells by scientists, convert sunlight directly into electricity. PV gets its name from the process of converting light (photons) to electricity (voltage), which is called the PV effect. Traditional solar cells are made from silicon, are usually flat-plate, and generally are the most efficient. Second-generation solar cells are called thin-film solar cells because they are made from amorphous silicon or non-silicon materials such as cadmium telluride. Thin film solar cells use layers of semiconductor materials only a few micrometers thick. Because of their flexibility, thin film solar cells can double as rooftop shingles and tiles, building facades, or the glazing for skylights. Third-generation solar cells are being made from a variety of new materials besides silicon, including solar inks using conventional printing press technologies, solar dyes, and conductive plastics. Some new solar cells use plastic lenses or mirrors to concentrate sunlight onto a very small piece of high efficiency PV material. The PV material is more expensive, but because so little is needed, these systems are becoming cost effective for use by utilities and industry.
1.4. Photovoltaic Systems
Photovoltaic system or solar power system is a power system designed to supply usable solar power by means of photo-voltaic. It consists of an arrangement of several components, including solar panels to absorb and convert sunlight into electricity, a solar inverter to change the electric current from DC to AC, as well as mounting, cabling and other electrical accessories to set up a working system. It may also use a solar tracking system to improve the system's overall performance and include an integrated battery solution, as prices for storage devices are expected to decline. Strictly speaking, a solar array only encompasses the ensemble of solar panels, the visible part of the PV system, and does not include all the other hardware, often summarized as balance of system. Moreover, PV systems convert light directly into electricity and shouldn't be confused with other technologies, such as concentrated solar power or solar thermal, used for heating and cooling. PV systems range from small, rooftop-mounted or building-integrated systems with capacities from a few to several tens of kilowatts, to large utility-scale power stations
4
of hundreds of megawatts. Nowadays, most PV systems are grid-connected, while off-grid or stand-alone systems only account for a small portion of the market. Operating silently and without any moving parts or environmental emissions, PV systems have developed from being niche market applications into a mature technology used for mainstream electricity generation.
Fig 1.2 Components of PV system
1.4.1 Solar cell
The basic element of a PV System is the photovoltaic (PV) cell, also called a Solar Cell. An example of a PV / Solar Cell made of Mono-crystalline Silicon. This single PV / Solar Cell are like a square but with its four corners missing (it is made this way). A PV / Solar Cell is a semiconductor device that can convert solar energy into DC electricity through the Photovoltaic effect (Conversion of solar light energy into electrical energy). When light shines on a PV / Solar Cell, it may be reflected, absorbed, or passes right through. But only the absorbed light generates electricity
5
Fig1.3 Construction and working of PV solar cell
1.4.2. PV module / panel and PV array
Photovoltaic cells are connected electrically in series and/or parallel circuits to produce higher voltages, currents and power levels. Photovoltaic modules consist of PV cell circuits sealed in an environmentally protective laminate, and are the fundamental building blocks of PV systems. Photovoltaic panels include one or more PV modules assembled as a pre-wired, field installable
unit. A photovoltaic array is the complete power-generating unit, consisting of any number of
Figure 1.4: Solar cell, Module and array
PV modules and panels. To increase their utility, a number of individual PV cells are interconnected together in a sealed, weatherproof package called a Panel (Module). For example, a 12 V Panel (Module) will have 36 cells connected in series and a 24 V Panel (Module) will have 72 PV Cells connected in series to achieve the desired voltage and current, Modules are wired in
6
series and parallel into what is called a PV Array. The flexibility of the modular PV system allows designers to create solar power systems that can meet a wide variety of electrical needs.
The cells are very thin and fragile so they are sandwiched between a transparent front sheet, usually glass, and a baking sheet, usually glass or a type of tough plastic. This protects them from breakage and from the weather. An aluminum frame is fitted around the module to enable easy fixing to a support structure.
Fig 1.5 Construction of typical monocrystalline PV/Solar cell
1.5. Pvlib Python
The proper modelling of a photovoltaic (PV) system is critical to its technical and financial success. Many commercial integrated software packages are available and accepted in industry: for example, PVsyst, Helioscope, SAM, Watts and others provide the ability for designers to assess the potential output and revenue from a PV system. These packages are particularly adept at answering the following design questions:
• Overall system output given irradiance information.
• Sizing and specification of major components (inverters, panels, combiners).
• Shading and loss factors analysis.
And they are able to provide these results in a form which is accepted in the technical and financial industries (i.e., bankable). This is due to the traceability of their algorithms and the
7
familiarity of the industry with these outputs. However, because of the integrated nature of these simulations’ packages, there is a lack in flexibility of simulations which the package can perform. This means that designers and researchers cannot create customized and integrated tools for exploring advanced topics in PV performance analysis. These advanced tools are often required to perform detailed analyses of system performance, and to allow innovation in the deployment of PV technologies.
Thus, those requiring the ability to perform more advanced data analysis will generally create custom algorithms in programs such as MATLAB, R, Python, or in spreadsheet programs. These algorithms are generally based on published literature or understood industry best practice, however the process of creating new algorithms based on these sources is time consuming and can lead to errors or mis-interpretations, and are generally difficult to individually validate. In order to address these issues, Sandia National Laboratories has developed PV LIB, a collaboratively developed open-source PV modeling environment. This environment consists of modeling algorithms which can be used in isolation or in combination to analyse all portions of the PV system modeling work flow. The backbone of pvlib-python is well-tested procedural code that implements PV system models. pvlib-python also provides a collection of classes for users that prefer object-oriented programming. These classes can help users keep track of data in a more organized way, provide some “smart” functions with more flexible inputs, and simplify the modelling process for common situations. The classes do not add any algorithms beyond what’s available in the procedural code, and most of the object methods are simple wrappers around the corresponding procedural code. Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built-in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development, as well as for use as a scripting or glue language to connect existing components together. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance. Python supports modules and packages, which encourages program modularity and code reuse.
8
The Python interpreter and the extensive standard library are available in source or binary form without charge for all major platforms, and can be freely distributed. Pvlib Python is a general-purpose PV modelling toolkit written in Python. Pvlib Python originated as a port of PVLib MATLAB and contains many of the MATLAB project’s features. The Pvlib Python and MATLAB projects are developed independently, but some developers contribute to both projects. PVLib Python is a dependency of other open-source tools. PVLib Python includes extensive function-level documentation, and a collection of examples in its online documentation and Jupyter notebooks. 1.6. Orientation of report
CHAPTER 1: This chapter includes Introduction to Solar, what is pvlib python and orientation
CHAPTER 2: This chapter includes Mathematical modelling of PV cell and characteristic of pv module.
CHAPTER 3: This chapter includes Pvlib concepts and Simulated graph for different irradiance and temperature values
CHAPTER 4: This chapter compares between Python and Matlab
CHAPTER 5: This chapter includes case studies of when temperature and irradiance are taken constant
CHAPTER 6: This chapter includes conclusion of the report
9
CHAPTER 2
MATHEMATICAL MODELLING OF PV SYSTEM
2.1. Introduction
Mathematical modelling of PV system includes calculating a module IV curve for certain operating conditions is a two-step process. De Soto model used to calculate the electrical parameters for an IV curve at a certain irradiance and temperature using the module’s base characteristics at reference conditions. The single-diode equation is a circuit-equivalent model of a PV cell and has five electrical parameters that depend on the operating conditions. Those parameters are then used to calculate the module’s IV curve by solving the single-diode equation using the Lambert W method.
2.2. Single Diode Equivalent Circuit Model Equivalent circuit models define the entire I-V curve of a cell, module, or array as a continuous function for a given set of operating conditions. One basic equivalent circuit model in common use is the single diode model, which is derived from physical principles represented by the following circuit for a single solar cell:
Figure 2.1: Single Diode Equivalent Circuit Model The governing equation for this equivalent circuit is formulated using Kirchhoff’s current law for current : (1)
10
Here, represents the light-generated current in the cell, represents the voltage-dependent current lost to recombination, and represents the current lost due to shunt resistances. In this single diode model, is modeled using the Shockley equation for an ideal diode: (2) where is the diode ideality factor (unitless, usually between 1 and 2 for a single junction cell), is the saturation current, and is the thermal voltage given by: (3) where is Boltzmann’s constant and is the elementary charge . Writing the shunt current as and combining this and the above equations results in the complete governing equation for the single diode model: (4) The five parameters in this equation are primary to all single diode equivalent circuit models: • : light current (A) • : diode reverse saturation current (A) • : series resistance () • : shunt resistance () • : diode ideality factor (unitless) For a photovoltaic module or array comprising cells in series, and assuming all cells are identical and under uniform and equal irradiance and temperature (i.e., generate equal current and voltage), and The single diode equation for a module or array becomes:
11
(5) where and are the current and voltage, respectively, of the module or array. Care should be taken when implementing model parameters, as they are either applicable to a cell, module, or array. Parameters for modules or arrays are strictly used with the single diode equation for , which is the more commonly implemented form. In some implementations the thermal voltage , diode ideality factor , and number of cells in series are combined into a single variable termed the modified ideality factor: . (6) The following equivalent circuit module models are described. These models have been proposed with different sets of auxiliary equations that describe how the primary parameters of the single diode equation change with cell temperature and irradiance. Module models, or those with parameters applicable to a module using , are examined here instead of those for cells or arrays because module models are the basic performance models used for modeling arrays in PV modeling software packages. 2.3. De Soto “Five-Parameter” Module Model The De Soto model, also known as the five-parameter model, uses the following equations to express each of the five primary parameters as a function of cell temperature and total absorbed irradiance : • (7) • (8) • (9) •
12
• (10) • Absorbed irradiance, , is equal to plane of array( POA )irradiance reaching the PV cells (including incident angle reflection losses but not spectral mismatch). In each equation, the subscript “ref” refers to a value at reference conditions. In De Soto et al., 2006, the modified ideality factor is used, and expressed as a linear function of cell temperature , which is equivalent to a constant diode ideality factor . , termed the “air mass modifier”, represents the spectral effect, from changing atmospheric air mass and corresponding absorption, on the light current. is the polynomial in air mass from the Sandia PV Array Performance Model (SAPM). The term is the temperature coefficient (A/K) of short-circuit current, set equal to the temperature coefficient of the light current. The term is the temperature-dependent bandgap (eV); given as the simplified first order Taylor series of the experimental bandgap temperature. The empirical constant 0.0002677 is representative of silicon cells at typical operating temperatures, and it is used for all cell technologies. 2.4. PVsyst Module Model PVsyst is a software package for modeling complete photovoltaic systems including PV modules, inverters, energy storage, and electrical connection components. PVsyst employs a single diode module model with the following ancillary equations. Note that here we use and to denote the light current, absorbed irradiance and temperature coefficient of , respectively, whereas in the PVsyst User’s Guide, , , and are used for these quantities. (11) (12)
13
In the PVsyst User’s Guide, is used to denote the diode quality (ideality) factor where we use . The bandgap voltage term is regarded as constant in PVsyst and values are provided for various technologies (e.g., 1.12 eV for cSi) in the PVsyst User’s Guide. (13) (14) In the PVsyst User’s Guide, is written as and is written as ; is a function of irradiance , and is the value of the shunt resistance at the reference irradiance . The term is a constant The PVsyst User’s Guide provides an option to use a temperature-dependent diode factor expressed as: (15) For amorphous modules, PVsyst modifies the single diode equation to account for recombination current losses : (16) by modeling the loss as a controlled current drain as represented in the following equivalent circuit: Figure 2.2: Single Diode Equivalent Circuit Model for pv system module
14
The recombination current is governed by: (17) Inclusion of this current sink changes the standard single diode equation to: (18) where is the thickness of the intrinsic layer that separates the p and n junctions, is the voltage potential across the intrinsic layer, and is the effective diffusion length of the charge carrier. In implementation, per junction is typical , and the quantity is combined into a single parameter. 2.5. The Lambert W method The Lambert W function is used to solve equations in which the unknown quantity occurs both in the base and in the exponent, or both inside and outside of a logarithm. The strategy is to convert such an equation into one of the forms zez = w and then to solve for z. 2.6. Solar Cell I-V Characteristic Curve The Solar Cell I-V Characteristic Curves shows the current and voltage (I-V) characteristics of a particular photovoltaic (PV) cell, module or array. It gives a detailed description of its solar energy conversion ability and efficiency. Knowing the electrical I-V characteristics (more importantly Pmax) of a solar cell, or panel is critical in determining the device’s output performance and solar efficiency. Photovoltaic solar cells convert the suns radiant light directly into electricity. With increasing demand for a clean energy source and the sun’s potential as a free energy source, has made solar energy conversion as part of a mixture of renewable energy sources increasingly
15
important. As a result, the demand for efficient solar cells, which convert sunlight directly into electricity, is growing faster than ever before. Photovoltaic (PV) cells are made almost entirely from semiconductor silicon that has been processed into an extremely pure crystalline material which absorbs the photons from sunlight. The photons hit the silicon atoms releasing electrons causing an electric current to flow when the photoconductive cell is connected to an external load. For example, a battery. There are a variety of different measurements we can make to determine the solar cell’s performance, such as its power output and its conversion efficiency. The main electrical characteristics of a PV cell or module are summarized in the relationship between the current and voltage produced on a typical solar cell I-V characteristics curve. The intensity of the solar radiation (insolation) that hits the cell controls the current ( I ), while the increases in the temperature of the solar cell reduces its voltage ( V ).Solar cells produce direct current (DC) electricity and current times voltage equals power, so we can create solar cell I-V curves representing the current versus the voltage for a photovoltaic device. Figure 2.3: Solar Cell I-V Characteristics Curves
16
Photovoltaic panels can be wired or connected together in either series or parallel combinations, or both to increase the voltage or current capacity of the solar array. If the array panels are connected together in a series combination, then the voltage increases and if connected together in parallel then the current increases. The electrical power in Watts, generated by these different photovoltaic combinations will still be the product of the voltage times the current, ( P = V x I ). However the solar panels are connected together, the upper right hand corner will always be the maximum power point (MPP) of the array. Figure 2.4 : IV characteristics when series or parallel cells connected together 2.7. Conclusion Solar Cell I-V Characteristics Curves are basically a graphical representation of the operation of a solar cell or module summarizing the relationship between the current and voltage at the existing conditions of irradiance and temperature in terms of single diode equivalent circuit and parameters are further modified by DeSoto 5 parameter model and lambert w function. I-V curves provide the information required to configure a solar system so that it can operate as close to its optimal peak power point (MPP) as possible.
17
CHAPTER 3 GENERATING IV CURVES 3.1. Introduction Python is a computer programming language often used to build websites and software, automate tasks, and conduct data analysis. In order to draw I-V curves, we import a software open-source python package pvlib-python. The core mission of pvlib-python is to provide an open, reliable, interoperable, and benchmark implementations of PV system models. It provides a set of documented functions for simulating the performance of photovoltaic energy systems. The toolbox was originally developed in MATLAB at Sandia National Laboratories and it implements many of the models and methods developed at the Labs. The development of simulation models in Pvlib will serve as the foundation for future work where optimization algorithms will be implemented to maximize yield while reducing system cost. 3.2. Pvlib Python
The Python programming language is a free and open-source programming environment which has been shown to be very well suited to scientific computations. A key feature of Python is its flexibility to handle computation from small scale to large highly parallelized high performance computing operations and because of this is able to scale easily, with no costs, to a user’s demands and requirements.
In addition, the Python language is supported by a vibrant community of developers, and new features are actively added and maintained. Because of this, integration with web, database and graphically intensive processes are relatively simple and intuitive in the system, allowing for a greater flexibility when developing models and algorithms.
Python is also designed to be easily written and interpreted, and because of the high-level nature of the code is easily learned and understood by those with a basic understanding of programming syntax.
18
As PV LIB develops into the Python programming language, it will feature three main principles:
• Take advantage of the Python programming language, to ensure free access to academic and commercial users
• Designed for collaborative development, and backed by a rigorous method to include the contributions of authors and researchers into the package
• Backed by a full testing and validation suite- to ensure stability of the package and to allow for validation of model results against real-world performance data.
3.3. Pvlib Concept
The vision for PV LIB is to become a standard repository for high quality PV related analysis algorithms. This code is open-source, collaboratively developed and validated, and it is hoped that the release of this code will accelerate the development of the PV industry for the following reasons:
• Create a linkage between researchers and implementors Authors of new algorithms can present them in a format which can be adopted into modeling work flows quickly and at a low cost.
• Provide validated tools to groups which do not have the ability to develop them Many industry and research groups do not have the ability to develop algorithms for advanced data analysis, and are limited by the capabilities of spreadsheet software and commercial integrated analysis packages.
• Increase the efficiency of PV research Many research projects in PV performance require the development of an initial testing and modeling suite before new research can begin. By providing a high quality and validated toolset for the basis of research, the rate of innovation can be accelerated.
• Enable faster, reliable model inter-comparisons and validations Models integrated into the PV LIB Package can be easily compared and validated in a reproducible way.
19
• Increase the quality of communication between developers, Independent Engineers (IEs), and financiers by providing a common modeling platform for advanced data analysis, the communication of complex data analysis can be simplified and shared in a reproducible way.
• Provide tools to efficiently handle large datasets The analysis of data on hourly or minutely timescales can provide valuable insights into system performance, and spreadsheet programs are generally not able to handle the volume of data associated with these datasets. Using efficient code and the ability to parallelize some operations means that high resolution data can be analysed.
• Collaboration can increase the pace of technology innovation in the sector Because the future expansion of PV LIB will be based on the contributions of the PV community, new analysis methodologies and best practices can be quickly adopted by the sector.
3.4. Using Pvlib for python
PV LIB is created in the Python programming language, and can used alongside a powerful suite of Python modules to enable powerful options for data analysis including:
Figure 3.1: Example of PV LIB tools being used in Jupyter notebook to perform analysis.
20
• NumPy Numerical and statistical analysis tool-set • Matplotlib is a plotting library for Python. It is used along with NumPy to provide an environment that is an effective open-source alternative for MATLAB.
• Pandas Time series analysis tool-set, including time zone and daylight savings handling, and time series statistical operations
The predominant method used by users to interact with PV LIB is through the Jupyter Notebook which is shown in Figure 3.1, and allows users to create shareable workflows. These workflows can contain all processing steps from data input, to modeling, to statistical analysis. The libraries used for Pvlib is included in Jupyter Notebook which makes easy for any end user.
3.5. Installing Pvlib Most users install pvlib-python using the conda package manager in the Anaconda Python distribution. Anaconda is an open-source distribution of the Python and R programming languages for data science that aims to simplify package management and deployment. To install the most recent stable release of pvlib-python in a non-editable way, use one of the following commands to install pvlib-python:
# Get the package from the pvlib conda channel
# Best option for installing pvlib in the base Anaconda distribution
conda install -c pvlib pvlib
3.6. Input Parameters parameter data type description and units Technology string one of “Mono-c-Si”, “Multi-c-Si”, “Thin Film”, “CdTe”, or “CIGS” families of cells PTC float nameplate in W at PVUSA test conditions (1-sun, 20° ambient temperature, 1-m/s windspeed)
21
parameter data type description and units A_c float module area in m² Length float module length in m; Width float module width in m; N_s int number of cells in series I_sc_ref float short circuit current in A at reference condition V_oc_ref float open circuit voltage in V at reference condition I_mp_ref float max power current in A at reference condition V_mp_ref float max power voltage in V at reference condition alpha_sc float short circuit current temperature coefficient in A/Δ°C beta_oc float open circuit voltage temperature coefficient in V/Δ°C T_NOCT float normal operating cell temperature in °C a_ref float diode ideality factor I_L_ref float light or photogenerated current at reference condition in A I_o_ref float diode saturation current at reference condition in A R_s float series resistance in Ω R_sh_ref float shunt resistance at reference condition in Ω Adjust float adjustment to short circuit temperature coefficient in % gamma_r float power temperature coefficient at reference condition in %/Δ°C
Table 3.1: List of input parameters
3.7. Generating iv curves IV curve of PV module calculated for certain operating conditions is a two-step process. Multiple methods exist for both parts of the process. De Soto model is used to calculate the electrical parameters for an IV curve at a certain irradiance and temperature using the module’s base characteristics at reference conditions. Those parameters are then used to calculate the module’s IV curve by solving the single-diode equation using the Lambert W method.
22
The single-diode equation is a circuit-equivalent model of a PV cell and has five electrical parameters that depend on the operating conditions. This way uses pvlib.pvsystem.calcparams_desoto() to calculate the 5 electrical parameters needed to solve the single-diode equation. pvlib.pvsystem.singlediode() is then used to generate the IV curves.

3.8. Outputs
The simulation results for above are shown below for different inputs of irradiance and temperature values and they match with the ideal iv curve.
Figure 3.2: Output graph obtained for different temperature and irradiance values
25
The short circuit, open circuit and peak values of current, voltages power values obtained from reference values taken as'I_sc_ref': 5.1,'V_oc_ref': 59.4,'I_mp_ref': 4.69,'V_mp_ref': 46.9, and the temperature and irradiance are (1000, 55), (900, 4(700, 35), (600, 25), (400, 15), (200, 10)
are shown below i_sc v_oc i_mp v_mp p_mp 0 5.235561 52.129782 4.742475 39.614015 187.868468 1 4.672568 54.264230 4.262116 42.179621 179.774427 2 3.604533 56.013187 3.309576 44.855044 148.451162 3 3.063272 58.055325 2.825434 47.396719 133.916314 4 2.025184 59.477647 1.875831 49.819541 93.453047 5 1.008620 58.986152 0.936081 50.343073 47.125218
Table 3.2: Values of P_mp,V ,I for different values of temperature and irradiance
3.9. Conclusion
Pvlib python is a tool used for calculating IV curves of PV module of 96 cells with rating of 200.1 Short circuit current and open circuit voltages are considered as references with varying irradiances and temperature are fed to de so to model of PVLIB which generates open circuit voltages ,short circuit current and peak power is obtained for respective voltages and currents.
26
CHAPTER 4
PYTHON VS MATLAB
4.1. Introduction MATLAB is a multi-paradigm numerical computing environment and programming platform that provides the ability to analyse data, create models, develop algorithms, and create applications. Python is a high-level programming language with dynamic semantics and a simple, easy-to-learn syntax designed with general-purpose programming.
Python, by definition, is a programming language. The most common implementation is that in C (also known as CPython) and is what is mostly referred to as "Python". Apart from the programming language and interpreter, Python also consists of an extensive standard library. This library is aimed at programming in general and contains modules for os specific stuff, threading, networking, databases, etc.
MATLAB is a commercial numerical computing environment and programming language. The concept of MATLAB refers to the whole package, including the IDE. The standard library does not contain as much generic programming functionality, but does include matrix algebra and an extensive library for data processing and plotting. For extra functionality the MathWorks provides toolkits.
To do scientific computing in Python, you need additional packages (e.g., NumPy, SciPy, Matplotlib). Additionally, you'll need an IDE. Many pythoneers come from a Linux environment and use a Python shell and an editor (like vi or Emacs), but people coming from Matlab prefer a feature-rich IDE (us included). There are a handful of IDE's available, some of which are for free.
Because Python is open and free, it is very easy for other parties to design packages or other software tools that extend Python. It is possible to create applications using any of the mayor GUI libraries (e.g., Qt), use OpenGL, drive your USB port, etc. Another example is Cython to enhance the speed of algorithms by converting Python to C code, and PyInstaller to create a standalone application from your source.
Each package is being developed by a different (but often overlapping) group of people, who are also users of the package. Many packages are available for different purposes. In this open-source ecosystem, most packages are driven by a handful of core developers, but many of a package users
27
contribute to the development by reporting issues, helping with documentation, and making small improvements to the code.
Figure 4.1: Diagram illustrating the differences between Python and Matlab in terms of their ecosystem.
4.2. Advantages of Matlab
Matlab has its advantages:
• It has a solid number of functions.
• Simulink is a product for which there is no good alternative yet.
• It might be easier for beginners, because the package includes all you need, while in Python you need to install extra packages and an IDE. (Pyzo tries to solve this issue.)
• It has a large scientific community; it is used on many universities (although few companies have the money to buy a license).
4.3. The problem with Matlab
We do not intend to make Matlab look bad. We used to love Matlab ourselves! However, we think that Matlab has a few fundamental shortcomings. Most of these arise from its commercial nature:
28
• The algorithms are proprietary, which means you cannot see the code of most of the algorithms you are using and have to trust that they were implemented correctly.
• Matlab is quite expensive, which means that code that is written in Matlab can only be used by people with sufficient funds to buy a license.
• Naturally, the MathWorks puts restrictions on code portability, the ability to run your code on someone else’s computer. You can run your "compiled" application using the Matlab Component Runtime (MCR), but your portable app must exactly match the version of the installed MCR, which can be a nuisance considering that Matlab releases a new version every 6 months.
• The proprietary nature also makes it difficult/impossible for 3th parties to extend the functionality of Matlab.
Furthermore, there are some other issues that stem from MATLAB’s origins as a matrix manipulation package:
• The semicolon. It can be useful to show the result when you type code in the console, but in scripts it does not make any sense that one must end a line with a semicolon in order to suppress output.
• Indexing is done with braces rather than brackets, making it difficult to distinguish it from a function call.
4.4. Advantages of Python
• Free. As in speech and as in beer. (It won't cost you a thing, and you are allowed to view and modify the source.)
• Beautiful programming language. Python was created to be a generic language that is easy to read, while Matlab started as a matrix manipulation package to which they added a programming language. As you become more familiar with Python, you will be amazed with how well it is designed.
• Powerful. Because it's well designed, it's easier than other languages to transform your ideas into code. Further, Python comes with extensive standard libraries, and has a powerful datatype such as lists, sets and dictionaries. These really help to organize your data.
• Namespaces. Matlab supports namespaces for the functions that you write, but the core of Matlab is without namespaces; every function is defined in the global namespace. Python works with modules, which you need to import if you want to use them. (For example, from skimage import morphology.) Therefore, Python starts up in under a
29
second. Using namespaces gives structure to a program and keeps it clean and clear. In Python everything is an object, so each object has a namespace itself. This is one of the reasons Python is so good at introspection.
• Introspection. This is what follows from the object-oriented nature of Python. Because a program has a clear structure, introspection is easy. Private variables only exist by convention, so you can access any part of the application, including some of Python's internals. Of course, in good programming practice you would not use private variables of other classes, but it's great for debugging!
• String manipulation. This is incredibly easy in Python. What about this line of code which returns a right justified line of 30 characters: "I code in Matlab".replace('MATLAB’, ‘Python').rjust(30)
• Portability. Because Python is for free, your code can run everywhere. Further, it works on Windows, Linux, and OS X.
• Class and function definitions. Functions and classes can be defined anywhere. In one file (whether it is a module or a script) you can design as many functions and classes as you like. You can even define one in the command shell if you really want to ...
• Great GUI toolkits. With Python you can create a front-end for your application that looks good and works well. You can choose any of the major GUI toolkits like Wx or Qt.
4.5. PVLIB PYTHON vs PVLIBMATLAB
Two Versions
PVLib Matlab is a general-purpose PV modeling toolkit for the Matlab platform It is primarily developed at Sandia National Laboratories, but contains contributions from members of the PV Performance Modeling Collaborative (PVPMC; see www.pvpmc.org). PVLib Matlab includes extensive documentation and extensive examples.
PVLib Python is a general-purpose PV modeling toolkit written in Python PVLib Python originated as a port of PVLib Matlab and contains many of the Matlab project’s features. The PVLib Python and Matlab projects are developed independently, but some developers contribute to both projects. PVLib Python is a dependency of other open-source tools. PVLib Python includes
30
extensive function-level documentation, and a collection of examples in its online documentation and Jupyter notebooks.
PVLIBMATLAB
PVLIB PYTHON
•Integrates with Matlab environment (help, search)
•Extensively tested by Sandia National Laboratories
• No extra toolboxes required
• Requires Matlab license ($$)
• Not fully integrated into GitHub (yet)
• Updates have been slow to be released.
• No formal way report/fix bugs except for email.
• Free
• Can be integrated with a huge ecosystem of Python libraries
• Comprehensive unit tests
• A real Python library, not just a wrapper with awkward syntax
• High-level features that do not (yet?) exist in PVLIB MATLAB
• A growing community on GitHub
• Getting started with Python, NumPy, SciPy can be challenging
• Not as many functions as PVLIB MATLAB
Table 4.1: Differences between PV LIB PYTHON and PVLIB MATLAB
4.6. Conclusion
The PV LIB is a Python software package developed by Sandia National Laboratories. The intention of this open-source package is to accelerate the pace of innovation in the PV sector through providing a powerful, validated set of tools for the modeling of PV system performance. The intention of this package is to develop along with the industry and to serve as a common repository for new and developing techniques prior to their inclusion in commercial integrated modeling software, and to enable users to gain deeper insight into their data analysis and enable faster, reliable model inter-comparisons and validations.
31
CASE STUDY 1: EFFECT OF IRRADIANCE
The solar irradiance effect on electrical characteristics of PV module are simulated under solar irradiance of 200 W/m2 , 400 W/m2 , 600 W/m2 , 800 W/m2 , 1000 W/m2 and constant temperature of 400C. The current-voltage and power-voltage curve of PV module are shown in Figure. The Figure shows that under constant temperature the value of the open circuit voltage scales logarithmically with the short circuit current which, in turn scales linearly with the solar irradiance resulting in a logarithmic dependence of the open circuit voltage with the solar irradiance. The solar irradiance effect on the electrical characteristics of PV module is much larger in the short circuit current than in the open circuit voltage. The value of the short circuit current and the open circuit voltage of each the solar irradiance can be seen in table.
Figure 5.1: Current-voltage curve of PV module with 200 W/m2, 400 W/m2, 600 W/m2 , 800 W/m2 , 1000 W/m2 of solar irradiance and 25 0C of constant temperature
32
i_sc v_oc i_mp v_mp p_mp 0 1.035839 51.321318 0.951608 42.577839 40.517430 1 2.070523 53.238566 1.901044 43.490203 82.676790 2 3.104054 54.360083 2.846160 43.659238 124.261168 3 4.136434 55.155812 3.786246 43.528510 164.809638 4 5.167666 55.773026 4.720672 43.237877 204.111821
Table 5.1: Current-voltage values of PV module with 200 W/m2, 400 W/m2, 600 W/m2 , 800 W/m2 , 1000 W/m2 of solar irradiance and 25 0C of constant temperature
Figure shows that under constant temperature, if the solar irradiance increase causes the maximum power of PV module will increase. The value of the PV module maximum power of each the solar irradiance can be seen in Table. Table shows that under constant temperature, if the solar irradiance increase causes the electrical characteristics of PV module (short circuit current, open circuit voltage, maximum power, and efficiency) will increase, the fill factor is fulfilled.
33
CASE STUDY 2: EFFECT OF TEMPERATURE
The temperature effect on the electrical characteristics of PV module is simulated under constant solar irradiance of 1000 W/m2 and temperature of 25 0C, 35 0C, 45 0C, 55 0C, 65 0C. The current-voltage curve of PV module is shown in Figure. Figure shows that under constant solar irradiance and difference temperature, the open circuit voltage and short circuit current of PV module will be influenced significantly and slightly, respectively. The open circuit voltage tends to decrease with increasing temperature. When temperature increase, the amount of saturation current will increase more than the amount of photocurrent and therefore makes the open circuit voltage decreased rapidly. The short-circuit circuit tends to increase with increasing temperature. The photocurrent generated by the PV module is the sum of electron diffusion current, hole diffusion current and dominant generation current in the depletion region. The generation current in the ideal depletion region is independent of temperature, so the increase of diffusion will result in an increase of photocurrent. The value of the short circuit current and the open circuit voltage of each the temperature can be seen in Table
.
Figure 5.2: Current-voltage curve of PV module under 800 W/m2 of constant solar irradiance and difference temperature.
34
Figure shows that under constant solar irradiance, if the temperature increase cause the maximum power of PV module will decrease. The value of the PV module maximum power of each the temperature can be seen in Table . Table shows that under constant solar irradiance, if the temperature increase cause the open circuit voltage, maximum power, and efficiency of PV module will decrease, but the short circuit current will increase, the fill factor is fulfilled.
i_sc v_oc i_mp v_mp p_mp 0 4.208896 50.255442 3.810396 38.657153 147.299078 1 4.172665 52.708976 3.800090 41.083442 156.120764 2 4.136434 55.155812 3.786246 43.528510 164.809638 3 4.100203 57.595708 3.769370 45.990277 173.354367 4 4.063972 60.028407 3.749880 48.466887 181.745024 5 4.027741 62.453632 3.728126 50.956668 189.972858
Table 5.2: Current-voltage values of PV module under 800 W/m2 of constant solar irradiance and difference temperature.
35
CONCLUSION
Solar Cell I-V Characteristics Curves are basically a graphical representation of the operation of a solar cell or module summarizing the relationship between the current and voltage at the existing conditions of irradiance and temperature in terms of single diode equivalent circuit. The electrical characteristics of PV module are dependent on solar irradiance and temperature. Change in irradiance will change the short circuit current and change in temperature will change the Open circuit voltage. If the solar irradiance is constant and the temperature increase will cause the open circuit voltage, maximum power and efficiency decrease, if the temperature constant and solar irradiance increase will cause the short circuit current, open circuit voltage, maximum power and efficiency increase. I-V curves provide the information required to configure a solar system so that it can operate as close to its optimal peak power point (MPP) as possible. PV system modelling software package, Pvlib is used to calculate performance curves of PV modules. In order to calculate the iv curves, mathematical modelling of PV cell Desoto five parameter model and Lambert W function is used. Outputs are simulated in Pvlib Python environment and peak power, current, voltage values are tabulated. It is concluded that using python to investigate the performance of photovoltaic cells is efficient in terms of time consuming when compared to other simulation programs. When the algorithm is used for larger models, the simulation takes additional time and processor usage, however it is faster than other methods Additionally, it is concluded that algorithm performs efficiently in terms of time and processor usage when comparing to other algorithms and simulation software’s, specially comparing to MATLAB.
36
REFERENCES
1. Review of open source tools for PV modeling William F. Holmgren1 , Clifford W. Hansen2 , Joshua S. Stein2 , and Mark A. Mikofski3 1 University of Arizona, Tucson, AZ, 85721, USA; 2 Sandia National Laboratories, Albuquerque, NM, 87122, USA
2. Y. T. Tan, D. S. Kirschen, and N. Jenkins, “A model of PV generation suitable for stability analysis,” IEEE Trans. Energy Convers., vol. 19, no. 4, pp. 748–755, Dec. 2004.
3. Effect of Solar Irradiance and Temperature on Photovoltaic Module Electrical Characteristics ,research gate,M. Irwanto* , I Daut* , M. Sembiring** , Rosnazri Bin Ali *, S. Champakeow *, and S. Shema*
4. A Review Paper on Improving The Efficiency Of Solar Panel ,IJRET,Shaikh Mohamadsaied Rubab1, Mulani Saifali Abbas2, Shinde Mayur Balasaheb 3, Chaure Balaji Mohan4
5. https://pvlib-python.readthedocs.io/en/v0.9.0/package_overview.html
6. https://pypi.org/project/solarpy/
7.https://www.researchgate.net/publication/286668952_Introduction_to_the_open_source_PV_LIB_for_8python_Photovoltaic_system_modelling_package
8. https://en.wikipedia.org/wiki/Theory_of_solar_cells
9. https://www.alternative-energy-tutorials.com/photovoltaics/solar-cell-i-v-characteristic.html#
10. https://assessingsolar.org/notebooks/solar_power_modeling.html#CharacteristicsPV
