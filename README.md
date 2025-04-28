# Treemap Visualization Project
# COMP4037 Coursework 2 MANALI AHIRRAO 20644125

# This script creates a Treemap showing environmental impacts 
# of different diet groups based on GHG emissions and biodiversity impact.

import pandas as pd
import plotly.express as px

# Load the dataset
# ( Results_21MAR2022_nokcaladjust.csv is in the same folder)
data = pd.read_csv('Results_21MAR2022_nokcaladjust.csv')

# Grouped the data by diet group, gender, and age group
grouped_data = data.groupby(['diet_group', 'sex', 'age_group']).agg({
    'mean_ghgs': 'mean',   # Greenhouse gas emissions
    'mean_bio': 'mean'     # Biodiversity impact
}).reset_index()

# Create the Treemap
fig = px.treemap(
    grouped_data,
    path=['diet_group', 'sex', 'age_group'],  # Create hierarchy
    values='mean_ghgs',                      # Size mapped to GHG emissions
    color='mean_bio',                        # Color mapped to biodiversity loss
    color_continuous_scale='YlGnBu',
    color_continuous_midpoint=grouped_data['mean_bio'].median(),
    labels={
        'diet_group': 'Diet Group',
        'sex': 'Gender',
        'age_group': 'Age Group',
        'mean_ghgs': 'GHG Emissions (kg CO2e)',
        'mean_bio': 'Biodiversity Impact (species/day)'
    }
)
fig.update_layout(
    title="Environmental Footprint by Diet Group, Gender, and Age Group",
    font=dict(size=14),
    height=900,
    paper_bgcolor='white',
    plot_bgcolor='white'
)

# HTML save GITHUB
fig.write_html('treemap_visualization_fixed.html', full_html=True, include_plotlyjs='cdn')

print(" Treemap saved as 'treemap_final_visualization_.html' successfully!")
