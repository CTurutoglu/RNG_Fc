In this document, the integration codes and methods for the RNG k-epsilon turbulence model variant, 
introduced as RNG Fc, are shared for various CFD solvers. 
Researchers are encouraged to investigate the model in complex flow cases 
and contribute to its further development.

Thanks!


/!\ Limitations /!\

1- Working fluid must be an ideal-gas.
2- Energy equation must be computed.


	Ansys 23 R1

	CFX

i.	Add the expressions given in "ANSYS_CFX_23R1.txt" file
ii.	Select the "standard k-epsilon" turbulence model in the Domain Tab
iii.	In the "Advanced Turbulence Model" tab, change "Cmu" coefficient to 0.085 and the "Compressible Production" to the value 1
iv.	Create a new subdomain
v.	In the subdomain tab, add a new source to Turbulence Dissipation Rate equation in the "Source" tab and write the expression "RNGSource"
Note: "u*" should be limited if the freestream intensity is low with "ustar limiter = t" and "ustar limiter coef = 0.1"
(researcher may use different limiter coefficient values depenging on their experience) in CFX.

	Fluent
i.	Add the expressions given in "ANSYS_Fluent_23R1.txt" file or import "ANSYS_Fluent_23R1.txt" file to the Named Expressions
ii.	Select the "k-epsilon" turbulence model in the "Viscous" pane and keep "k-epsilon Model" option to Standard
iii.	In the "Model Constants" tab, change "Cmu" coefficient to 0.085
iv.	Go to "Cell Zone Conditions" and open your fluid zone
v.	Click on "Source Term" option in your fluid zone pane
vi.	Go to "Source Terms" tab in the pane and click to "Edit" for Turbulent Dissipation Rate equation
vii.	Change the "Number of Turbulent Dissipation Rate sources" to 1 and choose "expression" option on the scroll, write "Source" as expression
