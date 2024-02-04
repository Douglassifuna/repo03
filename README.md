# repo03
import streamlit as st
import pandas as pd
import matplotlib.pyplot as plt

# Data
data = {
    'Zeolite': ['CLO', 'TSC', 'ITV', 'FAU', 'IFV', 'RWY', 'IRY', 'HypABCB', 'SBE', 'IFT', 'EMT', 'IRR', 'ITT', 'SBS', 'SYT', 'UTL', 'DFO'],
    'Loading (mol/cell)': [40, 11, 10, 7, 6, 6, 5, 5, 4, 4, 3, 3, 2, 2, 2, 2, 2]
}

df = pd.DataFrame(data)

# Streamlit App
st.title('Zeolite Loading Showcase')
st.subheader('Research Data')

# Display the data table
st.dataframe(df)

# Bar chart for visualization
st.subheader('Zeolite Loading Visualization')
fig, ax = plt.subplots()
ax.bar(df['Zeolite'], df['Loading (mol/cell)'])
plt.xticks(rotation=45, ha='right')
plt.tight_layout()

# Display the bar chart using Streamlit
st.pyplot(fig)
