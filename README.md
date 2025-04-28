
# Environmental Impact Treemap Visualization

This project creates a Treemap to visualize the environmental impacts of different diet groups.  
The visualization shows greenhouse gas emissions and biodiversity impact for each group, separated by gender and age group.

## Files Included
- `treemap_visualization_student_version.py`: Python script to generate the Treemap.
- `treemap_visualization.html`: Output file showing the interactive Treemap.
- `Results_21MAR2022_nokcaladjust.csv`: Dataset used (from University of Oxford research).

## How to Run

   ```
   pip install pandas plotly
   ```
 Place the CSV file and the Python script in the same folder.
Run the script:
   ```
   python treemap_visualization_student_version.py
   ```
Open the generated `treemap_visualization.html` file in a web browser to view the Treemap.

## About the Visualization
- **Box Size** = Mean GHG Emissions (kg CO₂e)
- **Box Color** = Mean Biodiversity Impact (species extinction/day)
- **Hierarchy** = Diet Group → Gender → Age Group

## Author
Manali A  
COMP4037 Coursework 2

## Reference
Scarborough, P., Clark, M., Cobiac, L. et al. (2023).  
Vegans, Vegetarians, Fish-eaters and Meat-eaters in the UK Show Discrepant Environmental Impacts. *Nature Food*. https://doi.org/10.1038/s43016-023-00795-w
