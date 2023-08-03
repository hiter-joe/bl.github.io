1. Visulation: output
2. <ParameterList name="visualization">
    <Parameter name="visualize on 3D mesh" type="bool" value="true" />
    <ParameterList name="domain">
      <Parameter name="file name base" type="string" value="sub_long" />
      <Parameter name="times start period stop 0" type="Array(double)" value="{0.0,216000.0,-1.0}" />
      <Parameter name="times start period stop 1" type="Array(double)" value="{0.0,21600.0,216000.0}" />
      <Parameter name="times start period stop 2" type="Array(double)" value="{0.0,1080.0,21600.0}" />   // By doing this, the user can have time-dependent output
    </ParameterList>
    <ParameterList name="surface">
      <Parameter name="file name base" type="string" value="sur_long" />
      <Parameter name="times start period stop 0" type="Array(double)" value="{0.0,216000.0,-1.0}" />
      <Parameter name="times start period stop 1" type="Array(double)" value="{0.0,21600.0,216000.0}" />
      <Parameter name="times start period stop 2" type="Array(double)" value="{0.0,1080.0,21600.0}" />
    </ParameterList>
  </ParameterList>
  
  
