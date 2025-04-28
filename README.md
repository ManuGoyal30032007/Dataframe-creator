import streamlit as st
import pandas as pd
st.title("Dataframe Creator")
num_columns = st.number_input("Enter the number of columns you want in your data:", min_value=1, step=1)
num_rows = st.number_input("Enter the number of rows you want in your data:", min_value=1 , step=1)
if num_columns > 0 and num_rows > 0:
    data = {}
    for i in range(num_columns):
        Name_Column = st.text_input("Name of the column: ", key = f"name_input_{i}")
        if Name_Column :
            column_data = []
            for c in range(num_rows):
                data_columns = st.text_input("Enter the data you want to store", key = f"name_input_{i}_{c}")
                column_data.append(data_columns)
            data[Name_Column]= column_data
    if data:
        df = pd.DataFrame(data)
        st.write("Generated dataframe")
        st.dataframe(df)
        
