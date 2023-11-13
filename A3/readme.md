Assignment 3

Laust, Daniel & Mathias

----------

# Introduction and concept

  

The pre-construction and construction phase of a building project is often plagued by miscommunication and mistakes. Not only can this create delays, but it can also lead to large unexpected expenses and a worse performing building overall. Scheduling and logistics is a difficult and immensely important factor for securing a successful project. This is why we have developed our concept script.

What if detailed construction plans and data aiding scheduling could be automatically extracted from a building model using IFC and code? By automatically gathering data on building elements including shape, dimensions, materials, weight etc. it could be possible to create a tool which calculates the required construction vehicles, logistics of installation, necessary workforce, and much more for a project. Doing this would greatly aid the construction process. It would become easier to go from design to product. All in all, through this optimization, a lot of money and time could be spared.

To showcase this idea for a construction scheduling and logistics tool, we have created a simple version using IfcOpenShell and BlenderBIM. The script goes through each window element in an IFC model and calculates the necessary transportation method to get the window to the construction site, whether the window can be carried by two people, and whether a crane is required for installation. Furthermore, the script automatically writes this data into the IFC file as a new property set so the information can be easily shared and accessed with the building model.

  

This is but one simple implementation of the grand idea. With more time and coding experience, it could be possible to do this in a more detailed sense for all building elements in a model. Moreover, based on this information and more like it, it could be possible to automatically generate complete scheduling plans with information on transportation method and amount, installation details with required equipment, necessary personnel etc. In the following report, our concept and implementation are presented.

# Model use

As described, the designed tool is meant to analyze different parameters of all window elements in a building. From the window width, height, and placement, which can be extracted automatically with IfcOpenShell, it is able to tell whether or not a window can be mounted simply by workers, or if a crane is needed. Furthermore, the tool calculates the weight of the window and tells if it is possible for two people to carry it. As for transportation, based on the dimensions, the tool can tell which type of van or truck is necessary based on its size capacity. Within the scope of this assignment, three different transportation types have been implemented. This includes:

  

-   Van type G4 (dimensions: 2 x 4,2 x 2,3 m, load capacity: 805 kg)
    
-   Van type H4 (dimensions: 1,8 x 3,5 x 2 m, load capacity: 1214 kg)
    
-   5 axeled truck (load capacity: 47000 kg)
    

Within the code, it is specified that a window can be carried by two people if it weighs less than 80 kg, based on the health recommendation of a maximum carried weight of 50 kg per person. A crane is required if the window is placed higher than 1.5 m above ground and the window area is above 1.5 m^2, or if the area is above 6 m^2, making manual transportation highly impractical. These specifications can be easily altered in the script to fit specific needs, however, for a tool based on this concept to become useful on a larger scale, it will be necessary to build upon standards for healthy work conditions.

  

The intended audience for this tool is the 4D-modelling team and similar roles responsible for logistics and scheduling regarding a building project. They can utilize the tool to optimize construction and potentially decrease the number of hours spent in meetings regarding logistics and economics, which in turn will result in an overall cheaper, more efficient, and successful project plan.

In conclusion, by automatically knowing the minimum requirements for transportation, installation, and workforce for each building element, one can create an efficient construction schedule with minimal use of vehicles and personnel.

# Designing the process

To showcase the processes of the tool, we have created IDM diagrams in BPMN files. These are attached with the assignment. The first version shows the current integrated use case, whereas the second shows the ideal concept implementation with additional functions. We have shortly described the process for the window example, and as for the second version, it will function similarly but for all building elements with more information outflow.

  

The process starts with concepts of the overall building form, which is determined by the design team and architect in collaboration with the building owner and investors, who will have certain criterias to the overall form of the building. The next step in the process is to determine initial window placements and sizing of the windows. This is again done by the design team and architect. When these steps have been finished, the window tool is then used to create information that will be utilized by the logistics team, scheduling team, economics team and design team. From this step in the process, the following information is created:

  

-   Design model with detailed windows and drawings
    
-   Logistical and economical analysis
    
-   Finalized schedule for installation of windows
    

  

The next step is to determine whether the current sizing and placements of the windows satisfy all requirements based on the information given by the teams. It is unlikely that all requirements are satisfied after just one cycle of the process. Therefore, it is most likely that the information will be sent back to the design team and architect for a second iteration. After X amounts of iterations, when the requirements are met, the final window placements, sizing, and detailing are done, and the process will end.

# Information Exchange

The level of detail (LOD) required for the tool to be used is approximately LOD 200. Here, windows are appearing and their locations and sizes are known, which are crucial for the tool to function properly. The tool doesn’t need to receive information that is LOD 300, which includes glazing and frames, because the tool won’t use it. However, a further implementation of the concept could include elements at this level.

From a BIM perspective, the tool doesn’t change the LOD after execution. However, it changes the dynamics and helps to define boundaries for other teams within the project as a whole. The team responsible for the design of the windows will have defined dimensions to work with. Furthermore, if supply shortages on certain window sizes occur, it will be easier to determine what kind of impact it has on the logistics and economics, by returning information to the tool. In this way, an iterative process is promoted in order to minimize money and time spent.

For the tool to work properly between all departments of the BIM Project, the tool should be used in the early phases of the design process. Hereby, maximizing the amount of information exchanges in collaboration with this tool should result in a minimized number of required interaction between departments further on in the project as the LOD rises.

# Value

The tool provides business value through increased efficiency in the time management department. It automises a part of the time manager's job, which allows the manager more time to focus on other aspects of the project.

For large buildings with numerous windows, the manual decision of whether workers or a crane is needed for each window is tremendously time consuming, and may create errors. By automating the process, based on the provided inputs, the tool will decrease the likelihood of errors happening in the decision process.

Additionally, the tool optimizes the transportation logistics by calculating the window size and determining the most appropriate van for transporting the windows. This optimization has the potential to induce cost savings and decreased vehicle usage.

Furthermore, the tool can contribute to environmental impact reductions. This is done through its ability to optimize transport logistics and to determine the appropriate transportation vehicle, potentially leading to less fuel usage and thereby lessen the carbon footprint of the window transportation phase in construction.
