# Offline Fennel
An offline biogeochemical model within the Regional Ocean Modeling System (ROMS).

- fennel.h : Addition of new tracers and their respective equations: phosphate (PO4), river detritus for N and C (RIVER_DON), and new oxygen computation: RW14_OXYGEN_SC. 

- fennel_def.h : Definition of new input parameters in fennel_def.h. R_P2N (phyto phosphate:nitrogen ratio), K_PO4 (inverse half saturation for phytoplankton PO4 uptake), RDeRRN and RDeRRC (Remineralization rate for river detritus N and C).

- fennel_inp.h : Reads input parameters from Fennel configuration file. Addition of R_P2N (phyto phosphate:nitrogen ratio), K_PO4 (inverse half saturation for phytoplankton PO4 uptake), RDeRRN and RDeRRC (Remineralization rate for river detritus N and C).

- fennel_mod.h : allocation of new parameters for Fennel model.

- fennel_var.h : assigns metadata indices for the new variables PO4, RDeN and RDeC

- fennel_wrt.h : write out Fennel model parameters into output NetCDF files R_P2N, K_PO4, RDeRRN and RdeRRC

- globaldefs.F : if OFFLINE & OFFLINE_BIOLOGY automatically activate ATCLIMATOLOGY for processing and allocating active tracers (T & S). Indispensable for Fennel model as temp is used for light limitation for phytoplankton growth and salt for O2 saturation.

- checkdefs.F : new options for checking C-processing options: PO4 (adds PO4 dynamics), RIVER_DON (adds river detritus equation), RIVER_BIOLOGY & BIOLOGY (river biology point sources).

- checkvars.F : if defined OFFLINE & ATCLIMATOLOGY, get active tracers (variables T & S).

- set_data.F : change set sea surface height climatology, set 3D momentum climatology not accessing subsequent time step value.
