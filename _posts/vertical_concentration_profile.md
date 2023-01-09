# state file generated using paraview version 5.10.0

# uncomment the following three lines to ensure this script works in future versions
#import paraview
#paraview.compatibility.major = 5
#paraview.compatibility.minor = 10

#### import the simple module from the paraview
from paraview.simple import *
#### disable automatic camera reset on 'Show'
paraview.simple._DisableFirstRenderCameraReset()

# ----------------------------------------------------------------
# setup views used in the visualization
# ----------------------------------------------------------------

# Create a new 'Line Chart View'
lineChartView1 = CreateView('XYChartView')
lineChartView1.ViewSize = [682, 753]
lineChartView1.LegendPosition = [360, 711]
lineChartView1.LeftAxisRangeMaximum = 0.8
lineChartView1.BottomAxisRangeMinimum = -14.0
lineChartView1.BottomAxisRangeMaximum = 6.0
lineChartView1.RightAxisRangeMaximum = 6.66
lineChartView1.TopAxisRangeMaximum = 6.66

# get the material library
materialLibrary1 = GetMaterialLibrary()

# Create a new 'Render View'
renderView1 = CreateView('RenderView')
renderView1.ViewSize = [682, 753]
renderView1.AxesGrid = 'GridAxes3DActor'
renderView1.CenterOfRotation = [107.07119750976562, 0.0, -5.857500076293945]
renderView1.StereoType = 'Crystal Eyes'
renderView1.CameraPosition = [107.07119750976562, -416.4681618632436, -5.857500076293945]
renderView1.CameraFocalPoint = [107.07119750976562, 0.0, -5.857500076293945]
renderView1.CameraViewUp = [0.0, 0.0, 1.0]
renderView1.CameraFocalDisk = 1.0
renderView1.CameraParallelScale = 107.78989196904675
renderView1.BackEnd = 'OSPRay raycaster'
renderView1.OSPRayMaterialLibrary = materialLibrary1

SetActiveView(None)

# ----------------------------------------------------------------
# setup view layouts
# ----------------------------------------------------------------

# create new layout object 'Layout #1'
layout1 = CreateLayout(name='Layout #1')
layout1.SplitHorizontal(0, 0.500000)
layout1.AssignView(1, renderView1)
layout1.AssignView(2, lineChartView1)
layout1.SetSize(1365, 753)

# ----------------------------------------------------------------
# restore active view
SetActiveView(lineChartView1)
# ----------------------------------------------------------------

# ----------------------------------------------------------------
# setup the data processing pipelines
# ----------------------------------------------------------------

# create a new 'Xdmf3ReaderS'
vis_subsurface_dataVisItxmf = Xdmf3ReaderS(registrationName='vis_subsurface_data.VisIt.xmf', FileName=['C:\\Users\\libi292\\ats-short-course\\2022_ATs\\TEMPEST-Bing\\TEMPEST-Bing\\16_np1_test-tracer\\vis_subsurface_data.VisIt.xmf'])
vis_subsurface_dataVisItxmf.CellArrays = ['total_component_concentration.cell.C5H7O2N(aq)', 'total_component_concentration.cell.CH2O(aq)', 'total_component_concentration.cell.CO2(aq)', 'total_component_concentration.cell.N2(aq)', 'total_component_concentration.cell.NH4+', 'total_component_concentration.cell.NO2-', 'total_component_concentration.cell.NO3-', 'total_component_concentration.cell.O2(aq)', 'total_component_concentration.cell.tracer']

# create a new 'Cell Data to Point Data'
cellDatatoPointData1 = CellDatatoPointData(registrationName='CellDatatoPointData1', Input=vis_subsurface_dataVisItxmf)
cellDatatoPointData1.CellDataArraytoprocess = ['total_component_concentration.cell.C5H7O2N(aq)', 'total_component_concentration.cell.CH2O(aq)', 'total_component_concentration.cell.CO2(aq)', 'total_component_concentration.cell.N2(aq)', 'total_component_concentration.cell.NH4+', 'total_component_concentration.cell.NO2-', 'total_component_concentration.cell.NO3-', 'total_component_concentration.cell.O2(aq)', 'total_component_concentration.cell.tracer']

# create a new 'Plot Over Line'
plotOverLine1 = PlotOverLine(registrationName='PlotOverLine1', Input=cellDatatoPointData1)
plotOverLine1.Point1 = [75.07551558715316, 0.0, -14.842105241300509]
plotOverLine1.Point2 = [75.07551558715316, 0.0, 11.608216870797925]

# ----------------------------------------------------------------
# setup the visualization in view 'lineChartView1'
# ----------------------------------------------------------------

# show data from plotOverLine1
plotOverLine1Display = Show(plotOverLine1, lineChartView1, 'XYChartRepresentation')

# trace defaults for the display properties.
plotOverLine1Display.UseIndexForXAxis = 0
plotOverLine1Display.XArrayName = 'Points_Z'
plotOverLine1Display.SeriesVisibility = ['total_component_concentration.cell.CO2(aq)']
plotOverLine1Display.SeriesLabel = ['arc_length', 'arc_length', 'total_component_concentration.cell.C5H7O2N(aq)', 'total_component_concentration.cell.C5H7O2N(aq)', 'total_component_concentration.cell.CH2O(aq)', 'total_component_concentration.cell.CH2O(aq)', 'total_component_concentration.cell.CO2(aq)', 'total_component_concentration.cell.CO2(aq)', 'total_component_concentration.cell.N2(aq)', 'total_component_concentration.cell.N2(aq)', 'total_component_concentration.cell.NH4+', 'total_component_concentration.cell.NH4+', 'total_component_concentration.cell.NO2-', 'total_component_concentration.cell.NO2-', 'total_component_concentration.cell.NO3-', 'total_component_concentration.cell.NO3-', 'total_component_concentration.cell.O2(aq)', 'total_component_concentration.cell.O2(aq)', 'total_component_concentration.cell.tracer', 'total_component_concentration.cell.tracer', 'vtkValidPointMask', 'vtkValidPointMask', 'Points_X', 'Points_X', 'Points_Y', 'Points_Y', 'Points_Z', 'Points_Z', 'Points_Magnitude', 'Points_Magnitude']
plotOverLine1Display.SeriesColor = ['arc_length', '0', '0', '0', 'total_component_concentration.cell.C5H7O2N(aq)', '0.8899977111467154', '0.10000762951094835', '0.1100022888532845', 'total_component_concentration.cell.CH2O(aq)', '0.220004577706569', '0.4899977111467155', '0.7199969481956207', 'total_component_concentration.cell.CO2(aq)', '0.30000762951094834', '0.6899977111467155', '0.2899977111467155', 'total_component_concentration.cell.N2(aq)', '0.6', '0.3100022888532845', '0.6399938963912413', 'total_component_concentration.cell.NH4+', '1', '0.5000076295109483', '0', 'total_component_concentration.cell.NO2-', '0.6500038147554742', '0.3400015259021897', '0.16000610360875867', 'total_component_concentration.cell.NO3-', '0', '0', '0', 'total_component_concentration.cell.O2(aq)', '0.8899977111467154', '0.10000762951094835', '0.1100022888532845', 'total_component_concentration.cell.tracer', '0.220004577706569', '0.4899977111467155', '0.7199969481956207', 'vtkValidPointMask', '0.30000762951094834', '0.6899977111467155', '0.2899977111467155', 'Points_X', '0.6', '0.3100022888532845', '0.6399938963912413', 'Points_Y', '1', '0.5000076295109483', '0', 'Points_Z', '0.6500038147554742', '0.3400015259021897', '0.16000610360875867', 'Points_Magnitude', '0', '0', '0']
plotOverLine1Display.SeriesPlotCorner = ['Points_Magnitude', '0', 'Points_X', '0', 'Points_Y', '0', 'Points_Z', '0', 'arc_length', '0', 'total_component_concentration.cell.C5H7O2N(aq)', '0', 'total_component_concentration.cell.CH2O(aq)', '0', 'total_component_concentration.cell.CO2(aq)', '0', 'total_component_concentration.cell.N2(aq)', '0', 'total_component_concentration.cell.NH4+', '0', 'total_component_concentration.cell.NO2-', '0', 'total_component_concentration.cell.NO3-', '0', 'total_component_concentration.cell.O2(aq)', '0', 'total_component_concentration.cell.tracer', '0', 'vtkValidPointMask', '0']
plotOverLine1Display.SeriesLabelPrefix = ''
plotOverLine1Display.SeriesLineStyle = ['Points_Magnitude', '1', 'Points_X', '1', 'Points_Y', '1', 'Points_Z', '1', 'arc_length', '1', 'total_component_concentration.cell.C5H7O2N(aq)', '1', 'total_component_concentration.cell.CH2O(aq)', '1', 'total_component_concentration.cell.CO2(aq)', '1', 'total_component_concentration.cell.N2(aq)', '1', 'total_component_concentration.cell.NH4+', '1', 'total_component_concentration.cell.NO2-', '1', 'total_component_concentration.cell.NO3-', '1', 'total_component_concentration.cell.O2(aq)', '1', 'total_component_concentration.cell.tracer', '1', 'vtkValidPointMask', '1']
plotOverLine1Display.SeriesLineThickness = ['Points_Magnitude', '2', 'Points_X', '2', 'Points_Y', '2', 'Points_Z', '2', 'arc_length', '2', 'total_component_concentration.cell.C5H7O2N(aq)', '2', 'total_component_concentration.cell.CH2O(aq)', '2', 'total_component_concentration.cell.CO2(aq)', '2', 'total_component_concentration.cell.N2(aq)', '2', 'total_component_concentration.cell.NH4+', '2', 'total_component_concentration.cell.NO2-', '2', 'total_component_concentration.cell.NO3-', '2', 'total_component_concentration.cell.O2(aq)', '2', 'total_component_concentration.cell.tracer', '2', 'vtkValidPointMask', '2']
plotOverLine1Display.SeriesMarkerStyle = ['Points_Magnitude', '0', 'Points_X', '0', 'Points_Y', '0', 'Points_Z', '0', 'arc_length', '0', 'total_component_concentration.cell.C5H7O2N(aq)', '0', 'total_component_concentration.cell.CH2O(aq)', '0', 'total_component_concentration.cell.CO2(aq)', '0', 'total_component_concentration.cell.N2(aq)', '0', 'total_component_concentration.cell.NH4+', '0', 'total_component_concentration.cell.NO2-', '0', 'total_component_concentration.cell.NO3-', '0', 'total_component_concentration.cell.O2(aq)', '0', 'total_component_concentration.cell.tracer', '0', 'vtkValidPointMask', '0']
plotOverLine1Display.SeriesMarkerSize = ['Points_Magnitude', '4', 'Points_X', '4', 'Points_Y', '4', 'Points_Z', '4', 'arc_length', '4', 'total_component_concentration.cell.C5H7O2N(aq)', '4', 'total_component_concentration.cell.CH2O(aq)', '4', 'total_component_concentration.cell.CO2(aq)', '4', 'total_component_concentration.cell.N2(aq)', '4', 'total_component_concentration.cell.NH4+', '4', 'total_component_concentration.cell.NO2-', '4', 'total_component_concentration.cell.NO3-', '4', 'total_component_concentration.cell.O2(aq)', '4', 'total_component_concentration.cell.tracer', '4', 'vtkValidPointMask', '4']

# ----------------------------------------------------------------
# setup the visualization in view 'renderView1'
# ----------------------------------------------------------------

# show data from cellDatatoPointData1
cellDatatoPointData1Display = Show(cellDatatoPointData1, renderView1, 'UnstructuredGridRepresentation')

# get color transfer function/color map for 'total_component_concentrationcellCH2Oaq'
total_component_concentrationcellCH2OaqLUT = GetColorTransferFunction('total_component_concentrationcellCH2Oaq')
total_component_concentrationcellCH2OaqLUT.RGBPoints = [0.0, 0.231373, 0.298039, 0.752941, 0.0002171812520828098, 0.865003, 0.865003, 0.865003, 0.0004343625041656196, 0.705882, 0.0156863, 0.14902]
total_component_concentrationcellCH2OaqLUT.ScalarRangeInitialized = 1.0

# get opacity transfer function/opacity map for 'total_component_concentrationcellCH2Oaq'
total_component_concentrationcellCH2OaqPWF = GetOpacityTransferFunction('total_component_concentrationcellCH2Oaq')
total_component_concentrationcellCH2OaqPWF.Points = [0.0, 0.0, 0.5, 0.0, 0.0004343625041656196, 1.0, 0.5, 0.0]
total_component_concentrationcellCH2OaqPWF.ScalarRangeInitialized = 1

# trace defaults for the display properties.
cellDatatoPointData1Display.Representation = 'Surface'
cellDatatoPointData1Display.ColorArrayName = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
cellDatatoPointData1Display.LookupTable = total_component_concentrationcellCH2OaqLUT
cellDatatoPointData1Display.SelectTCoordArray = 'None'
cellDatatoPointData1Display.SelectNormalArray = 'None'
cellDatatoPointData1Display.SelectTangentArray = 'None'
cellDatatoPointData1Display.OSPRayScaleArray = 'total_component_concentration.cell.CH2O(aq)'
cellDatatoPointData1Display.OSPRayScaleFunction = 'PiecewiseFunction'
cellDatatoPointData1Display.SelectOrientationVectors = 'None'
cellDatatoPointData1Display.ScaleFactor = 21.414239501953126
cellDatatoPointData1Display.SelectScaleArray = 'total_component_concentration.cell.CH2O(aq)'
cellDatatoPointData1Display.GlyphType = 'Arrow'
cellDatatoPointData1Display.GlyphTableIndexArray = 'total_component_concentration.cell.CH2O(aq)'
cellDatatoPointData1Display.GaussianRadius = 1.0707119750976564
cellDatatoPointData1Display.SetScaleArray = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
cellDatatoPointData1Display.ScaleTransferFunction = 'PiecewiseFunction'
cellDatatoPointData1Display.OpacityArray = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
cellDatatoPointData1Display.OpacityTransferFunction = 'PiecewiseFunction'
cellDatatoPointData1Display.DataAxesGrid = 'GridAxesRepresentation'
cellDatatoPointData1Display.PolarAxes = 'PolarAxesRepresentation'
cellDatatoPointData1Display.ScalarOpacityFunction = total_component_concentrationcellCH2OaqPWF
cellDatatoPointData1Display.ScalarOpacityUnitDistance = 17.348011741278963
cellDatatoPointData1Display.OpacityArrayName = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']

# init the 'PiecewiseFunction' selected for 'ScaleTransferFunction'
cellDatatoPointData1Display.ScaleTransferFunction.Points = [0.0, 0.0, 0.5, 0.0, 2.5427934815525077e-06, 1.0, 0.5, 0.0]

# init the 'PiecewiseFunction' selected for 'OpacityTransferFunction'
cellDatatoPointData1Display.OpacityTransferFunction.Points = [0.0, 0.0, 0.5, 0.0, 2.5427934815525077e-06, 1.0, 0.5, 0.0]

# show data from plotOverLine1
plotOverLine1Display_1 = Show(plotOverLine1, renderView1, 'GeometryRepresentation')

# trace defaults for the display properties.
plotOverLine1Display_1.Representation = 'Surface'
plotOverLine1Display_1.ColorArrayName = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
plotOverLine1Display_1.LookupTable = total_component_concentrationcellCH2OaqLUT
plotOverLine1Display_1.SelectTCoordArray = 'None'
plotOverLine1Display_1.SelectNormalArray = 'None'
plotOverLine1Display_1.SelectTangentArray = 'None'
plotOverLine1Display_1.OSPRayScaleArray = 'total_component_concentration.cell.CH2O(aq)'
plotOverLine1Display_1.OSPRayScaleFunction = 'PiecewiseFunction'
plotOverLine1Display_1.SelectOrientationVectors = 'None'
plotOverLine1Display_1.ScaleFactor = 2.6450322151184085
plotOverLine1Display_1.SelectScaleArray = 'total_component_concentration.cell.CH2O(aq)'
plotOverLine1Display_1.GlyphType = 'Arrow'
plotOverLine1Display_1.GlyphTableIndexArray = 'total_component_concentration.cell.CH2O(aq)'
plotOverLine1Display_1.GaussianRadius = 0.1322516107559204
plotOverLine1Display_1.SetScaleArray = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
plotOverLine1Display_1.ScaleTransferFunction = 'PiecewiseFunction'
plotOverLine1Display_1.OpacityArray = ['POINTS', 'total_component_concentration.cell.CH2O(aq)']
plotOverLine1Display_1.OpacityTransferFunction = 'PiecewiseFunction'
plotOverLine1Display_1.DataAxesGrid = 'GridAxesRepresentation'
plotOverLine1Display_1.PolarAxes = 'PolarAxesRepresentation'

# init the 'PiecewiseFunction' selected for 'ScaleTransferFunction'
plotOverLine1Display_1.ScaleTransferFunction.Points = [1.458417522161249e-29, 0.0, 0.5, 0.0, 2.8056259537834194e-09, 1.0, 0.5, 0.0]

# init the 'PiecewiseFunction' selected for 'OpacityTransferFunction'
plotOverLine1Display_1.OpacityTransferFunction.Points = [1.458417522161249e-29, 0.0, 0.5, 0.0, 2.8056259537834194e-09, 1.0, 0.5, 0.0]

# setup the color legend parameters for each legend in this view

# get color legend/bar for total_component_concentrationcellCH2OaqLUT in view renderView1
total_component_concentrationcellCH2OaqLUTColorBar = GetScalarBar(total_component_concentrationcellCH2OaqLUT, renderView1)
total_component_concentrationcellCH2OaqLUTColorBar.Title = 'total_component_concentration.cell.CH2O(aq)'
total_component_concentrationcellCH2OaqLUTColorBar.ComponentTitle = ''

# set color bar visibility
total_component_concentrationcellCH2OaqLUTColorBar.Visibility = 1

# show color legend
cellDatatoPointData1Display.SetScalarBarVisibility(renderView1, True)

# show color legend
plotOverLine1Display_1.SetScalarBarVisibility(renderView1, True)

# ----------------------------------------------------------------
# setup color maps and opacity mapes used in the visualization
# note: the Get..() functions create a new object, if needed
# ----------------------------------------------------------------

# get color transfer function/color map for 'total_component_concentrationcellCO2aq'
total_component_concentrationcellCO2aqLUT = GetColorTransferFunction('total_component_concentrationcellCO2aq')
total_component_concentrationcellCO2aqLUT.RGBPoints = [9.779568443946118e-08, 0.231373, 0.298039, 0.752941, 0.3873449754935301, 0.865003, 0.865003, 0.865003, 0.7746898531913757, 0.705882, 0.0156863, 0.14902]
total_component_concentrationcellCO2aqLUT.ScalarRangeInitialized = 1.0

# get opacity transfer function/opacity map for 'total_component_concentrationcellCO2aq'
total_component_concentrationcellCO2aqPWF = GetOpacityTransferFunction('total_component_concentrationcellCO2aq')
total_component_concentrationcellCO2aqPWF.Points = [9.779568443946118e-08, 0.0, 0.5, 0.0, 0.7746898531913757, 1.0, 0.5, 0.0]
total_component_concentrationcellCO2aqPWF.ScalarRangeInitialized = 1

# ----------------------------------------------------------------
# restore active source
SetActiveSource(plotOverLine1)
# ----------------------------------------------------------------


if __name__ == '__main__':
    # generate extracts
    SaveExtracts(ExtractsOutputDirectory='extracts')
    
    
    
    
    Get the plotoverline
    
    
    
    then save all data into csv
    
    import csv
import matplotlib.pyplot as plt
import os

# Create a figure with a subplot for each column
fig, axs = plt.subplots(nrows=9, ncols=1, figsize=(16,50))

# Iterate over the files in the folder
for i in range(10,200,50):
    # Open the file and create a CSV reader
    filename = f'./data/reaction/200_{i}.csv'
    with open(filename) as f:
        reader = csv.reader(f)
        
        # Read the header row
        header = next(reader)
        y_col = header[-1]
        
        # Iterate over the columns
        for j, col in enumerate(header[1:10]):
            # Read the data for the column
            data = [float(row[j+1]) for row in reader]
            
            # Reset the file pointer and create a new CSV reader
            f.seek(0)
            
            next(reader)
            
            y_data = [float(row[-1]) for row in reader]
            
            # Reset the file pointer and create a new CSV reader
            f.seek(0)
            
            next(reader)
            # Plot the data for the column
            axs[j].plot(data, y_data, label=f'{i} day')
           
            title = col.rsplit('.', 1)[-1]
            axs[j].set_title(title)
            
            # Set the x-axis in log scale
            #axs[j].set_xscale('log')

            # Add a legend to the plot
            axs[j].legend()
            
             # Set the x-axis and y-axis labels
            axs[j].set_xlabel('Concentration [-]')
            axs[j].set_ylabel('H (m)')


plt.show()

    
    
