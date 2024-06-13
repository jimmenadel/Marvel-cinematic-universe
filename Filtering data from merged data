import pandas as pd


df=pd.DataFrame()
file1 = open('merged_data.txt', 'r')
Lines = file1.readlines()

count = 0
for line in Lines:
    count += 1
    titulo=line.strip()
    print("Line%d: %s"%(count,titulo))
    df2=pd.read_csv(titulo)
    df=pd.concat([df,df2], ignore_index=True)
    print(df)

X=(df[df["Personaje"].str.contains("/")])
newb= ""#newbefore
newa= ""#newafter
nameactor=" "
peli = " "
year= " "
persona= ""
for i in range(len(X)):
  persona= X.iloc[i]["Personaje"]
  nameactor= X.iloc[i]["Actor"]
  peli= X.iloc[i]["Pelicula"]
  year= X.iloc[i]["Año"]
  newb=persona.split("/")[-1]
  newa= persona.split("/")[0]
  Data=[newa, nameactor,peli,year]
  Index= ['Personaje', 'Actor', 'Pelicula', 'Año']
  mini_df = pd.DataFrame(Data, index=Index)
  row_index = df.loc[df["Actor"]== nameactor].index[1]
  df.loc[row_index, 'Personaje'] = newb
  df= pd.concat([mini_df], ignore_index = True)
