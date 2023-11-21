# extract-small-scale-systems-from-radiative-transfer-cosmological-sim

The main function which performs these functions 

1)  Reads the data cubes from Radiative Transfer Hydrodynamical simulation 
    the data cubes are Dark matter, Gas mass, temperature, 
    numbers densities of HI and HII and ne


  c```infile  = fopen(gammagridfilename.c_str(),"rb");
  cout<<"Reading file "<<gammagridfilename.c_str()<< endl;
  fread(gammaHI_cube, sizeof(float), NGRIDR, infile);
  cout << gammaHI_cube[0] <<" "<<gammaHI_cube[NGRIDR-1] << endl;
  fclose(infile);


  infile  = fopen(dmfilename.c_str(),"rb");
  cout<<"Reading file "<<dmfilename.c_str()<< endl;
  fread(dm_cube, sizeof(float), NGRIDR, infile);
  cout << dm_cube[0] <<" "<<dm_cube[NGRIDR-1] << endl;
  fclose(infile);


  infile  = fopen(gasdatagridfilename.c_str(),"rb");
  cout<<"Reading file "<<gasdatagridfilename.c_str()<< endl;

  fread(delta_cube, sizeof(float), NGRIDR, infile);
  fseek ( infile,   NGRID3D*4, SEEK_SET );
  fread(rhog_cube, sizeof(float), NGRIDR, infile);
  fseek ( infile,   2*NGRID3D*4, SEEK_SET );
  fread(temp_cube, sizeof(float), NGRIDR, infile);
  fseek ( infile, 3*NGRID3D*4, SEEK_SET );
  fread(nHI_cube, sizeof(float), NGRIDR, infile);
  fseek ( infile, 4*NGRID3D*4, SEEK_SET );
  fread(nHII_cube, sizeof(float), NGRIDR, infile);
  fseek ( infile, 5*NGRID3D*4, SEEK_SET );
  fread(ne_cube, sizeof(float), NGRIDR, infile);  
  fclose(infile);```


    
    
3) Find systems using 4-pixels connectivity in the data cube  

4) Calculate several quantites from these systems

	Position of maximum in HI field
	Total Mass
	Total dark matter mass in solar
	Size in [kpc/h]^3
	Gas temp [K]
	Radiation field Gamma
	HI enutral fraction HI_delta
	HI column densities NHI
