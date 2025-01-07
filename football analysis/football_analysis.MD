{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "883cfcf3-ec88-455c-ba98-5db5094574f0",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "import numpy as np"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "3bb27458-3891-4bba-ac74-627b77a2a8dd",
   "metadata": {},
   "source": [
    " # Load the dataset and display basic information"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "9d580a2b-8345-4530-8a79-ece34faba5c7",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PlayerID</th>\n",
       "      <th>Name</th>\n",
       "      <th>Team</th>\n",
       "      <th>Position</th>\n",
       "      <th>Goals</th>\n",
       "      <th>Assists</th>\n",
       "      <th>Appearances</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>Lionel Messi</td>\n",
       "      <td>Inter Miami</td>\n",
       "      <td>Forward</td>\n",
       "      <td>15</td>\n",
       "      <td>10</td>\n",
       "      <td>20</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>Cristiano Ronaldo</td>\n",
       "      <td>Al Nassr</td>\n",
       "      <td>Forward</td>\n",
       "      <td>18</td>\n",
       "      <td>5</td>\n",
       "      <td>21</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>Kylian Mbappe</td>\n",
       "      <td>PSG</td>\n",
       "      <td>Forward</td>\n",
       "      <td>22</td>\n",
       "      <td>6</td>\n",
       "      <td>19</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>Neymar Jr</td>\n",
       "      <td>Al Hilal</td>\n",
       "      <td>Forward</td>\n",
       "      <td>8</td>\n",
       "      <td>12</td>\n",
       "      <td>18</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>Kevin De Bruyne</td>\n",
       "      <td>Man City</td>\n",
       "      <td>Midfielder</td>\n",
       "      <td>5</td>\n",
       "      <td>16</td>\n",
       "      <td>22</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PlayerID               Name         Team    Position  Goals  Assists  \\\n",
       "0         1       Lionel Messi  Inter Miami     Forward     15       10   \n",
       "1         2  Cristiano Ronaldo     Al Nassr     Forward     18        5   \n",
       "2         3      Kylian Mbappe          PSG     Forward     22        6   \n",
       "3         4          Neymar Jr     Al Hilal     Forward      8       12   \n",
       "4         5    Kevin De Bruyne     Man City  Midfielder      5       16   \n",
       "\n",
       "   Appearances  \n",
       "0           20  \n",
       "1           21  \n",
       "2           19  \n",
       "3           18  \n",
       "4           22  "
      ]
     },
     "execution_count": 2,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "#Use pandas to load the dataset and display the first 5 rows, column names, and data types.\n",
    "football_data=pd.read_csv('football_data.csv')\n",
    "football_data.head()\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7d395b17-8098-47c6-9d17-4e738353b1e5",
   "metadata": {},
   "source": [
    "# Calculate total goals scored by all players"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "8bb01811-a735-44f3-a2a4-302e1118cde2",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "The total number of  goals scored by all players combined is 179\n"
     ]
    }
   ],
   "source": [
    "#Use pandas to calculate and display the total number of goals scored by all players combined.\n",
    "total_number_of_goals=football_data['Goals'].sum()\n",
    "print(f'The total number of  goals scored by all players combined is {total_number_of_goals}')"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "62b74d6b-334d-44ef-bb88-af946a1276aa",
   "metadata": {},
   "source": [
    "# Find the player with the highest number of assists"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "318cb652-1b52-47f5-9fc8-728e6d75c4a7",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "The player with the most assists is \"Kevin De Bruyne\",playing for \"Man City\" Team, with Total assist of \"16\"\n"
     ]
    }
   ],
   "source": [
    "#Identify the player with the most assists and display their name, team, and total assists.\n",
    "player=football_data.groupby('Name')['Assists'].max()\n",
    "max=football_data.groupby('Team')['Assists'].max()\n",
    "assist=football_data['Assists'].max()\n",
    "print(f'The player with the most assists is \"{player.idxmax()}\",playing for \"{max.idxmax()}\" Team, with Total assist of \"{assist}\"')\n",
    "\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "e7e3bc7b-84dd-41ff-ac83-faf227776caa",
   "metadata": {},
   "source": [
    "# Calculate the average goals per appearance\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "1602d63e-e798-4bb9-8a52-54b39d3f80b5",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PlayerID</th>\n",
       "      <th>Name</th>\n",
       "      <th>Team</th>\n",
       "      <th>Position</th>\n",
       "      <th>Goals</th>\n",
       "      <th>Assists</th>\n",
       "      <th>Appearances</th>\n",
       "      <th>GoalsPerAppearance</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>Lionel Messi</td>\n",
       "      <td>Inter Miami</td>\n",
       "      <td>Forward</td>\n",
       "      <td>15</td>\n",
       "      <td>10</td>\n",
       "      <td>20</td>\n",
       "      <td>0.750000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>Cristiano Ronaldo</td>\n",
       "      <td>Al Nassr</td>\n",
       "      <td>Forward</td>\n",
       "      <td>18</td>\n",
       "      <td>5</td>\n",
       "      <td>21</td>\n",
       "      <td>0.857143</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>Kylian Mbappe</td>\n",
       "      <td>PSG</td>\n",
       "      <td>Forward</td>\n",
       "      <td>22</td>\n",
       "      <td>6</td>\n",
       "      <td>19</td>\n",
       "      <td>1.157895</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>Neymar Jr</td>\n",
       "      <td>Al Hilal</td>\n",
       "      <td>Forward</td>\n",
       "      <td>8</td>\n",
       "      <td>12</td>\n",
       "      <td>18</td>\n",
       "      <td>0.444444</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>Kevin De Bruyne</td>\n",
       "      <td>Man City</td>\n",
       "      <td>Midfielder</td>\n",
       "      <td>5</td>\n",
       "      <td>16</td>\n",
       "      <td>22</td>\n",
       "      <td>0.227273</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PlayerID               Name         Team    Position  Goals  Assists  \\\n",
       "0         1       Lionel Messi  Inter Miami     Forward     15       10   \n",
       "1         2  Cristiano Ronaldo     Al Nassr     Forward     18        5   \n",
       "2         3      Kylian Mbappe          PSG     Forward     22        6   \n",
       "3         4          Neymar Jr     Al Hilal     Forward      8       12   \n",
       "4         5    Kevin De Bruyne     Man City  Midfielder      5       16   \n",
       "\n",
       "   Appearances  GoalsPerAppearance  \n",
       "0           20            0.750000  \n",
       "1           21            0.857143  \n",
       "2           19            1.157895  \n",
       "3           18            0.444444  \n",
       "4           22            0.227273  "
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "#For each player, calculate the average number of goals per appearance and add a new column to the DataFrame called GoalsPerAppearance.\n",
    "football_data['GoalsPerAppearance']=football_data['Goals']/football_data['Appearances']\n",
    "display(football_data.head())"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4d630cd1-536d-4edf-aa24-5f3b58bb8154",
   "metadata": {},
   "source": [
    "# Plot a bar chart of total goals per team"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "630ac495-558f-4775-b2f9-95d52576aefc",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAjIAAAIgCAYAAACf0oPJAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjguMCwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy81sbWrAAAACXBIWXMAAA9hAAAPYQGoP6dpAABrJElEQVR4nO3dd1RUV9cG8GcG6VUFBBQFBMWCvcZEjZ3YNXYFsSXWWBJLrJBEjYk1thQFNSoaa2xERSxRjBViVxAFu9EAigoC5/vDl/kYmiXMLfr81pq1mDt35uy5bIY95557jkYIIUBERESkQlq5AyAiIiJ6UyxkiIiISLVYyBAREZFqsZAhIiIi1WIhQ0RERKrFQoaIiIhUi4UMERERqRYLGSIiIlItFjJERESkWixk6K2wf/9+aDQabNiwQe5QJOHm5oa+ffvKHUa+sn4f+/fvlzsURdFoNJg2bVqB+ygxl18lbiK5sJAhxdJoNK90k/Kf5a1btzBt2jRERUW98Wvs3LmT/xSIiApJEbkDIMrPqlWr9O6vXLkSe/bsybW9QoUKuHDhgiQx3bp1C4GBgXBzc0O1atXe6DV27tyJRYsWsZghIioELGRIsXr37q13/+jRo9izZ0+u7QAkK2To3fTkyRNYWFjIHQbl4dmzZzAxMYFWyxMM7yr+5umtkpmZiW+++QalSpWCmZkZmjZtipiYmFz7/fXXX2jVqhVsbW1hYWGBRo0a4fDhwwW+9v79+1G7dm0AQEBAgO7UVkhIiG6f3377DTVr1oS5uTns7e3Ru3dv3Lx5U/d43759sWjRIgD6p86yfP/993jvvfdQvHhxmJubo2bNmv9prMSDBw/Qp08f2NjYwM7ODv7+/oiOjs4VNwDs27cPH3zwASwtLWFnZ4f27dvnKhCvX7+OIUOGoHz58jA3N0fx4sXRpUsXXLt27aWxXLlyBZ07d4aTkxPMzMxQqlQpdO/eHUlJSYXyvF9//RV16tSBhYUFihYtioYNG2L37t16+yxevBiVKlWCqakpXFxcMHToUCQmJurt07hxY1SuXBknT55Ew4YNYWFhgS+//BIAkJqaiqlTp8LT0xOmpqZwdXXF2LFjkZqaqvcaqampGDVqFBwcHGBtbY127drhxo0bLz1G2WVkZODLL7+Ek5MTLC0t0a5dOyQkJOgenzp1KoyNjXH//v1czx00aBDs7Ozw7NmzfF+/b9++sLKywtWrV9GyZUtYWlrCxcUFQUFBEEIUGNur5MHVq1eh0Wgwd+7cXM8/cuQINBoN1q5dq9t28+ZN9OvXDyVKlICpqSkqVaqE5cuX6z0va/xQaGgoJk2ahJIlS8LCwgLJycl4/vw5AgMD4eXlBTMzMxQvXhzvv/8+9uzZU+B7IfVjjwy9VWbOnAmtVovPP/8cSUlJmDVrFnr16oW//vpLt8++ffvg6+uLmjVrYurUqdBqtQgODkaTJk1w6NAh1KlTJ8/XrlChAoKCgjBlyhQMGjQIH3zwAQDgvffeAwCEhIQgICAAtWvXxowZM3D37l3Mnz8fhw8fxunTp2FnZ4dPPvkEt27dyvMUGQDMnz8f7dq1Q69evZCWlobQ0FB06dIF27dvR+vWrV/rWGRmZqJt27Y4duwYBg8eDG9vb2zduhX+/v659t27dy98fX3h4eGBadOm4enTp/jhhx/QoEEDnDp1Cm5ubgCA48eP48iRI+jevTtKlSqFa9euYcmSJWjcuDHOnz+fb69FWloaWrZsidTUVAwfPhxOTk64efMmtm/fjsTERNja2v6n5wUGBmLatGl47733EBQUBBMTE/z111/Yt28fWrRoAQCYNm0aAgMD0axZMwwePBiXLl3CkiVLcPz4cRw+fBjGxsa6dh88eABfX190794dvXv3RokSJZCZmYl27drhzz//xKBBg1ChQgWcOXMGc+fOxeXLl7Flyxbd8wcMGIBff/0VPXv2xHvvvYd9+/a99u/vm2++gUajwbhx43Dv3j3MmzcPzZo1Q1RUFMzNzdGnTx8EBQVh3bp1GDZsmN4x27BhAzp37gwzM7MC28jIyECrVq1Qr149zJo1C2FhYZg6dSrS09MRFBSU7/NeJQ88PDzQoEEDrF69GqNGjdJ7/urVq2FtbY327dsDAO7evYt69epBo9Fg2LBhcHBwwK5du9C/f38kJydj5MiRes//6quvYGJigs8//xypqakwMTHBtGnTMGPGDAwYMAB16tRBcnIyTpw4gVOnTqF58+avdexJZQSRSgwdOlTkl7IRERECgKhQoYJITU3VbZ8/f74AIM6cOSOEECIzM1N4eXmJli1biszMTN1+T548Ee7u7qJ58+YFxnD8+HEBQAQHB+ttT0tLE46OjqJy5cri6dOnuu3bt28XAMSUKVNe6X08efIk1+tWrlxZNGnSRG97mTJlhL+/f4Gxbty4UQAQ8+bN023LyMgQTZo0yfUeqlWrJhwdHcWDBw9026Kjo4VWqxV+fn75xieEEJGRkQKAWLlypW5b1u8jIiJCCCHE6dOnBQDx22+/FRhzTq/yvCtXrgitVis6duwoMjIy9B7L+h3fu3dPmJiYiBYtWujts3DhQgFALF++XLetUaNGAoBYunSp3mutWrVKaLVacejQIb3tS5cuFQDE4cOHhRBCREVFCQBiyJAhevv17NlTABBTp04t8D1nHbuSJUuK5ORk3fb169cLAGL+/Pm6bfXr1xd169bVe/6mTZv0jn1+/P39BQAxfPhw3bbMzEzRunVrYWJiIu7fv6/bnjPuV82DH3/8UQAQFy5c0G1LS0sT9vb2evnbv39/4ezsLP755x+91+zevbuwtbXVtZd1bDw8PHLFULVqVdG6desC3zO9nXhqid4qAQEBMDEx0d3P6jW5evUqACAqKgpXrlxBz5498eDBA/zzzz/4559/kJKSgqZNm+LgwYPIzMx87XZPnDiBe/fuYciQIXrfglu3bg1vb2/s2LHjlV7H3Nxc9/O///6LpKQkfPDBBzh16tRrxxQWFgZjY2MMHDhQt02r1WLo0KF6+92+fRtRUVHo27cvihUrpttepUoVNG/eHDt37swzvufPn+PBgwfw9PSEnZ1dgTFm9Zz88ccfePLkySu/h1d53pYtW5CZmYkpU6bkGieRddpu7969SEtLw8iRI/X2GThwIGxsbHL9fkxNTREQEKC37bfffkOFChXg7e2ty5t//vkHTZo0AQBEREQAgO54jRgxQu/5OXsVXsbPzw/W1ta6+x9//DGcnZ31fh9+fn7466+/EBsbq9u2evVquLq6olGjRq/UTvbenKwekbS0NOzduzff57xqHnTt2hVmZmZYvXq1btsff/yBf/75RzfWTQiBjRs3om3bthBC6B3bli1bIikpKVdu+fv768UAAHZ2djh37hyuXLnySu+b3h4sZOitUrp0ab37RYsWBfCiKACg+5Dz9/eHg4OD3u2XX35BamrqS8ds5OX69esAgPLly+d6zNvbW/f4y2zfvh316tWDmZkZihUrBgcHByxZsuSNY3J2ds51usfT0/OVY69QoYKu0AOAp0+fYsqUKXB1dYWpqSns7e3h4OCAxMTEAmN0d3fH6NGj8csv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xVy1RERERPS6WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLUWstURERMrnNn7Hf3r+tZmtCykSov/HHhkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItXi6tcK8V9XlQW4siwREb172CNDREREqsVChoiIiFSLhQwRERGpFgsZIiIiUi0WMkRERKRaLGSIiIhItVjIEBERkWqxkCEiIiLVYiFDREREqsVChoiIiFSLhQwRERGpFgsZIiIiUi0WMkRERKRaXP2aiIhUw238jv/0/GszWxdSJKQU7JEhIiIi1WIhQ0RERKrFQoaIiIhUi4UMERERqRYLGSIiIlItFjJERESkWixkiIiISLVYyBAREZFqsZAhIiIi1WIhQ0RERKrFQoaIiIhUi4UMERERqRYLGSIiIlItrn5NREREr+2/rkQOFM5q5OyRISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItWStZA5ePAg2rZtCxcXF2g0GmzZskXv8b59+0Kj0ejdWrVqJU+wREREpDiyFjIpKSmoWrUqFi1alO8+rVq1wu3bt3W3tWvXShghERERKZmsay35+vrC19e3wH1MTU3h5OQkUURERESkJoofI7N//344OjqifPnyGDx4MB48eFDg/qmpqUhOTta7ERER0dtJ0atft2rVCp06dYK7uztiY2Px5ZdfwtfXF5GRkTAyMsrzOTNmzEBgYOBrtaOUFTyJiIjo9Si6kOnevbvuZx8fH1SpUgVly5bF/v370bRp0zyfM2HCBIwePVp3Pzk5Ga6urgaPlYiIiKSn+FNL2Xl4eMDe3h4xMTH57mNqagobGxu9GxEREb2dVFXI3LhxAw8ePICzs7PcoRAREZECyHpq6fHjx3q9K3FxcYiKikKxYsVQrFgxBAYGonPnznByckJsbCzGjh0LT09PtGzZUsaoiYiISClkLWROnDiBDz/8UHc/a2yLv78/lixZgr///hsrVqxAYmIiXFxc0KJFC3z11VcwNTWVK2QiIiJSEFkLmcaNG0MIke/jf/zxh4TREBERkdqoaowMERERUXYsZIiIiEi1WMgQERGRahVKIZORkYGoqCj8+++/hfFyRERERK/kjQqZkSNHYtmyZQBeFDGNGjVCjRo14Orqiv379xdmfERERET5eqNCZsOGDahatSoAYNu2bYiLi8PFixcxatQoTJw4sVADJCIiIsrPGxUy//zzD5ycnAAAO3fuRJcuXVCuXDn069cPZ86cKdQAiYiIiPLzRoVMiRIlcP78eWRkZCAsLAzNmzcHADx58iTfVamJiIiICtsbTYgXEBCArl27wtnZGRqNBs2aNQMA/PXXX/D29i7UAImIiIjy80aFzLRp01C5cmUkJCSgS5cuuiUDjIyMMH78+EINkIiIiCg/b7xEwccff5xrm7+//38KhoiIiOh1vHIhs2DBgld+0REjRrxRMERERESv45ULmblz577SfhqNhoUMERERSeKVC5m4uDhDxkFERET02rjWEhEREanWGw/2vXHjBn7//XfEx8cjLS1N77E5c+b858CIiIiIXuaNCpnw8HC0a9cOHh4euHjxIipXroxr165BCIEaNWoUdoxEREREeXqjU0sTJkzA559/jjNnzsDMzAwbN25EQkICGjVqhC5duhR2jERERER5eqNC5sKFC/Dz8wMAFClSBE+fPoWVlRWCgoLw7bffFmqARERERPl5o0LG0tJSNy7G2dkZsbGxusf++eefwomMiIiI6CXeaIxMvXr18Oeff6JChQr46KOPMGbMGJw5cwabNm1CvXr1CjtGIiIiojy9USEzZ84cPH78GAAQGBiIx48fY926dfDy8uIVS0RERCSZNypkPDw8dD9bWlpi6dKlhRYQERER0at643lkAODkyZO4cOECAKBSpUqoXr16oQRFRERE9CreqJC5d+8eunfvjv3798POzg4AkJiYiA8//BChoaFwcHAozBiJiIiI8vRGVy0NHz4cjx49wrlz5/Dw4UM8fPgQZ8+eRXJyMheMJCIiIsm8UY9MWFgY9u7diwoVKui2VaxYEYsWLUKLFi0KLTgiIiKigrxRj0xmZiaMjY1zbTc2NkZmZuZ/DoqIiIjoVbxRIdOkSRN89tlnuHXrlm7bzZs3MWrUKDRt2rTQgiMiIiIqyBsVMgsXLkRycjLc3NxQtmxZlC1bFm5ubkhOTsYPP/xQ2DESERER5emNxsi4urri1KlTCA8P111+XaFCBTRr1qxQgyMiIiIqyGv1yDx9+hTbt28HAGg0GoSHhyMuLg5xcXHYuXMnxo4di2fPnhkkUCIiIqKcXqtHZsWKFdixYwfatGkD4MUppkqVKsHc3BwAcPHiRTg7O2PUqFGFHykRERFRDq/VI7N69WoMGjRIb9uaNWsQERGBiIgIfPfdd1i/fn2hBkhERESUn9cqZGJiYuDj46O7b2ZmBq32/1+iTp06OH/+fOFFR0RERFSA1zq1lJiYiNTUVN39+/fv6z2emZmp9zgRERGRIb1Wj0ypUqVw9uzZfB//+++/UapUqf8cFBEREdGreK1C5qOPPsKUKVPyvDLp6dOnCAwMROvWrQstOCIiIqKCvNappS+//BLr169H+fLlMWzYMJQrVw4AcOnSJSxcuBDp6en48ssvDRIoERERUU6vVciUKFECR44cweDBgzF+/HgIIQC8mFOmefPmWLx4MUqUKGGQQImIiIhyeu2Zfd3d3REWFoaHDx8iJiYGAODp6YlixYoVenBEREREBXmjJQoAoFixYqhTp05hxkJERET0Wt5o0UgiIiIiJWAhQ0RERKrFQoaIiIhUi4UMERERqRYLGSIiIlItFjJERESkWixkiIiISLVYyBAREZFqsZAhIiIi1WIhQ0RERKrFQoaIiIhUi4UMERERqRYLGSIiIlItFjJERESkWixkiIiISLVYyBAREZFqsZAhIiIi1WIhQ0RERKolayFz8OBBtG3bFi4uLtBoNNiyZYve40IITJkyBc7OzjA3N0ezZs1w5coVeYIlIiIixZG1kElJSUHVqlWxaNGiPB+fNWsWFixYgKVLl+Kvv/6CpaUlWrZsiWfPnkkcKRERESlRETkb9/X1ha+vb56PCSEwb948TJo0Ce3btwcArFy5EiVKlMCWLVvQvXt3KUMlIiIiBVLsGJm4uDjcuXMHzZo1022ztbVF3bp1ERkZme/zUlNTkZycrHcjIiKit5NiC5k7d+4AAEqUKKG3vUSJErrH8jJjxgzY2trqbq6urgaNk4iIiOSj2ELmTU2YMAFJSUm6W0JCgtwhERERkYEotpBxcnICANy9e1dv+927d3WP5cXU1BQ2NjZ6NyIiIno7KbaQcXd3h5OTE8LDw3XbkpOT8ddff6F+/foyRkZERERKIetVS48fP0ZMTIzuflxcHKKiolCsWDGULl0aI0eOxNdffw0vLy+4u7tj8uTJcHFxQYcOHeQLmoiIiBRD1kLmxIkT+PDDD3X3R48eDQDw9/dHSEgIxo4di5SUFAwaNAiJiYl4//33ERYWBjMzM7lCJiIiIgWRtZBp3LgxhBD5Pq7RaBAUFISgoCAJoyIiIiK1UOwYGSIiIqKXYSFDREREqsVChoiIiFSLhQwRERGpFgsZIiIiUi0WMkRERKRaLGSIiIhItVjIEBERkWqxkCEiIiLVYiFDREREqsVChoiIiFSLhQwRERGpFgsZIiIiUi0WMkRERKRaLGSIiIhItVjIEBERkWqxkCEiIiLVYiFDREREqsVChoiIiFSLhQwRERGpFgsZIiIiUq0icgdAlJ3b+B3/+TWuzWxdCJEQEZEasEeGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1WMgQERGRarGQISIiItViIUNERESqxUKGiIiIVIuFDBEREakWCxkiIiJSLRYyREREpFosZIiIiEi1FF3ITJs2DRqNRu/m7e0td1hERESkEEXkDuBlKlWqhL179+ruFymi+JCJiIhIIoqvCooUKQInJye5wyAiIiIFUvSpJQC4cuUKXFxc4OHhgV69eiE+Pr7A/VNTU5GcnKx3IyIioreTontk6tati5CQEJQvXx63b99GYGAgPvjgA5w9exbW1tZ5PmfGjBkIDAyUOFJ6m7iN3/GfX+PazNaFEAkREb2MontkfH190aVLF1SpUgUtW7bEzp07kZiYiPXr1+f7nAkTJiApKUl3S0hIkDBiIiIikpKie2RysrOzQ7ly5RATE5PvPqampjA1NZUwKiIiIpKLontkcnr8+DFiY2Ph7OwsdyhERESkAIouZD7//HMcOHAA165dw5EjR9CxY0cYGRmhR48ecodGRERECqDoU0s3btxAjx498ODBAzg4OOD999/H0aNH4eDgIHdoREREpACKLmRCQ0PlDoGIiIgUTNGn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",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Use matplotlib to create a bar chart that shows the total goals scored by players from each team.\n",
    "football_data.plot(kind='bar', x='Team', y='Goals', title='The total goals scored by players')\n",
    "plt.ylabel('Goals')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0e611e3e-ca03-41ec-b276-c905c8d5ba7a",
   "metadata": {},
   "source": [
    "# Group by position and calculate total goals and assists"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "a3170198-09b0-4539-9ade-ea045da422b4",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "            Goals  Assists\n",
      "Position                  \n",
      "Defender        6       24\n",
      "Forward       161       58\n",
      "Midfielder     12       40\n"
     ]
    }
   ],
   "source": [
    "#Group players by their position (Forward, Midfielder, Defender) and calculate the total goals and assists for each position.\n",
    "group_players=football_data.groupby('Position')[['Goals','Assists']].sum()\n",
    "print((group_players))"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "59f2e6bf-4b16-417e-93e6-fa3f5a81c0d7",
   "metadata": {},
   "source": [
    "# Scatter plot of Goals vs Assists "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "3fc031a8-8352-4cac-9e5a-3aeaeec673eb",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAjMAAAHHCAYAAABKudlQAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjguMCwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy81sbWrAAAACXBIWXMAAA9hAAAPYQGoP6dpAAA68klEQVR4nO3dd3gVZf7//9ch4aQQ0uiBkIROIMSVpqAUCYaIoYkguIqgYgEBWQt8RJooirvKLgLquguuBVlUirCKgBRRVIqxIh0BaYLCgQROSHL//uCb8+OQBBJMMmeS5+O6znVl5kx5z5w5zIt77pnjMMYYAQAA2FQFqwsAAAD4IwgzAADA1ggzAADA1ggzAADA1ggzAADA1ggzAADA1ggzAADA1ggzAADA1ggzAADA1ggzQDnUqVMnderUyeoyvBw5ckR9+/ZVlSpV5HA4NH36dKtLuqTY2FjdddddVpfhkyZOnCiHw2F1GShHCDMoM7777jv17dtXMTExCgwMVO3atdW1a1fNmDGjxNb59ttv53vSPXjwoCZOnKi0tLQSW7cVMjIyNHHiRK1Zs6bYl/3www9r+fLlGjt2rN544w1169btktO73W7NmDFD1113nSIiIuR0OhUVFaUePXpo3rx5ys7OLvYa7W7WrFlyOBxq27at1aXkUVa/MygdhBmUCZ9//rlatWqlb775Rvfee69eeukl3XPPPapQoYL+/ve/l9h6LxVmJk2aVOb+Yc7IyNCkSZNKJMx88skn6tmzpx555BH9+c9/VpMmTQqc9tdff1X79u01YsQIhYSEaNy4cXrllVf00EMPKT09XQMHDtQzzzxT7DXa3VtvvaXY2Fh99dVX2rlzZ4mtZ9y4cTpz5kyR5imr3xmUDn+rCwCKw9NPP62wsDBt3LhR4eHhXu8dPXrUmqJKQHp6uipVqmR1GSXi6NGjeT67gtxxxx36+uuv9d5776lPnz5e740dO1abNm3Stm3bSqBK+9qzZ48+//xzvf/++7rvvvv01ltvacKECSWyLn9/f/n7c3pBKTJAGdC4cWPTqVOnQk//xhtvmNatW5ugoCATHh5urr/+erN8+XLP+4sWLTI33XSTqVWrlnE6naZevXpm8uTJJisryzNNx44djSSvV0xMjFm9enWe8ZLMnDlzPPN+8cUXJjk52YSGhpqgoCDToUMHs379eq8aJ0yYYCSZH374wQwYMMCEh4ebq666qsBtmjNnjpFk1q5da4YOHWoiIyNN5cqVzR133GF+++03r2k7duxoOnbs6DXuyJEjZsiQIaZ69eomICDAtGjRwsydO9fz/p49e/LdrgkTJlxyX+/atcv07dvXREREmKCgINO2bVuzdOnSPHVf/CrI559/biSZ+++//5Lrvdjlti/X888/b6699loTGRlpAgMDzdVXX20WLFiQZ7qYmBgzaNAgz3BmZqaZOHGiadCggQkICDCRkZGmffv25uOPPy6wpo0bNxpJ+dbx0UcfGUnmgw8+MMYY43K5zMiRI01MTIxxOp2mWrVqJikpyWzevLlQ2//UU0+ZiIgI43a7zQMPPGAaNmyY73Tz5s0zV199tQkJCTGVK1c2zZs3N9OnTy/SduYeuxf6+OOPTfv27U1YWJipVKmSadSokRk7dqwxxlz2O7N9+3bTp08fU6NGDRMQEGBq165t+vfvb06cOFGobUfZR3RGmRATE6MNGzbo+++/V/PmzS857aRJkzRx4kS1a9dOkydPltPp1JdffqlPPvlEN954oyRp7ty5CgkJ0ejRoxUSEqJPPvlE48ePl8vl0vPPPy9JeuKJJ3Ty5EkdOHBAL774oiQpJCRETZs21eTJkzV+/HgNHTpU119/vSSpXbt2ks5fTklJSVHLli01YcIEVahQQXPmzNENN9ygTz/9VG3atPGq99Zbb1XDhg31zDPPyBhz2X0xfPhwhYeHa+LEidq2bZtmz56tn3/+WWvWrCmwU+aZM2fUqVMn7dy5U8OHD1dcXJwWLFigu+66SydOnNDIkSNVrVo1zZ49Ww888IB69+7taRFp0aJFgbUcOXJE7dq1U0ZGhkaMGKEqVaro9ddfV48ePfTuu++qd+/e6tChg9544w3dcccd6tq1q+68885Lbt8HH3wgSfrzn/982X1RlO3L9fe//109evTQ7bffrszMTL3zzju69dZbtXTpUnXv3r3AdUycOFFTp07VPffcozZt2sjlcmnTpk3asmWLunbtmu88rVq1Ur169fTf//5XgwYN8npv/vz5ioiIUHJysiTp/vvv17vvvqvhw4crPj5ex48f1/r167V161ZdffXVl90Hb731lvr06SOn06kBAwZo9uzZ2rhxo1q3bu2ZZsWKFRowYIC6dOmi5557TpK0detWffbZZ559dCXb+cMPP+jmm29WixYtNHnyZAUEBGjnzp367LPPJOmS35nMzEwlJyfL7XbroYceUs2aNfXLL79o6dKlOnHihMLCwi677SgHrE5TQHH4+OOPjZ+fn/Hz8zPXXnuteeyxx8zy5ctNZmam13Q7duwwFSpUML179zbZ2dle7+Xk5Hj+zsjIyLOO++67zwQHB5uzZ896xnXv3t3ExMTkmTb3f9wXtsbkrqNhw4YmOTk5z/ri4uJM165dPeNy/3c7YMCAQu2D3BaOli1bem33tGnTjCSzePFiz7iLW2amT59uJJk333zTMy4zM9Nce+21JiQkxLhcLmOMMb/++muhWmNyjRo1ykgyn376qWfcqVOnTFxcnImNjfX6DCSZYcOGXXaZvXv3NpLy/K/8zJkz5tdff/W8fv/99yJvnzF5P/vMzEzTvHlzc8MNN3iNv7hlJjEx0XTv3v2y9V9s7NixpmLFil6tZ26324SHh5shQ4Z4xoWFhRVq/+Rn06ZNRpJZsWKFMeb8cVinTh0zcuRIr+lGjhxpQkNDvVogL1aY7by4ZebFF180ksyvv/5a4DwFfWe+/vprIynf1jEgFx2AUSZ07dpVGzZsUI8ePfTNN99o2rRpSk5OVu3atbVkyRLPdIsWLVJOTo7Gjx+vChW8D/8LWy2CgoI8f586dUrHjh3T9ddfr4yMDP30009XXGdaWpp27NihgQMH6vjx4zp27JiOHTum9PR0denSRevWrVNOTo7XPPfff3+R1jF06FBVrFjRM/zAAw/I399f//vf/wqc53//+59q1qypAQMGeMZVrFhRI0aM0OnTp7V27doi1XDhctu0aaPrrrvOMy4kJERDhw7V3r179eOPPxZ5mS6Xy7OcC7388suqVq2a53XhOouyfRd+9r///rtOnjyp66+/Xlu2bLlkXeHh4frhhx+0Y8eOIm1P//79de7cOb3//vuecR9//LFOnDih/v37ey3/yy+/1MGDB4u0fOl8q0yNGjXUuXNnSeeP9f79++udd97xuusrPDxc6enpWrFiRYHLupLtzO0LtXjx4jzH9+XktrwsX75cGRkZRZoX5QdhBmVG69at9f777+v333/XV199pbFjx+rUqVPq27ev56S5a9cuVahQQfHx8Zdc1g8//KDevXsrLCxMoaGhqlatmueyxsmTJ6+4xtwTwKBBg7xOvNWqVdNrr70mt9udZ/lxcXFFWkfDhg29hkNCQlSrVi3t3bu3wHl+/vlnNWzYME/Aa9q0qef9K/Hzzz+rcePGecb/keVWrlxZknT69Gmv8bfccotWrFihFStW5Ln0VZTtW7p0qa655hoFBgYqMjLSc3ntcp/75MmTdeLECTVq1EgJCQl69NFH9e233152exITE9WkSRPNnz/fM27+/PmqWrWqbrjhBs+4adOm6fvvv1d0dLTatGmjiRMnavfu3ZddfnZ2tt555x117txZe/bs0c6dO7Vz5061bdtWR44c0apVqzzTPvjgg2rUqJFSUlJUp04dDRkyRB999NEf3s7+/furffv2uueee1SjRg3ddttt+u9//1uoYBMXF6fRo0frtddeU9WqVZWcnKyZM2f+oe8hyh7CDMocp9Op1q1b65lnntHs2bN17tw5LViwoNDznzhxQh07dtQ333yjyZMn64MPPtCKFSs8fQiK+j/LC+XO+/zzz3tOvBe/Lm5xuLClAPLcsv399997jY+OjlZSUpKSkpIUERFxRcv+9NNP1aNHDwUGBmrWrFn63//+pxUrVmjgwIGX7a/UoUMH7dq1S//+97/VvHlzvfbaa7r66qv12muvXXa9/fv31+rVq3Xs2DG53W4tWbJEt9xyi9cdQf369dPu3bs1Y8YMRUVF6fnnn1ezZs304YcfXnLZn3zyiQ4dOqR33nlHDRs29Lz69esn6XyrTa7q1asrLS1NS5YsUY8ePbR69WqlpKR49ee5ku0MCgrSunXrtHLlSt1xxx369ttv1b9/f3Xt2rVQzwP629/+pm+//Vb/93//pzNnzmjEiBFq1qyZDhw4cNl5UT4QZlCmtWrVSpJ06NAhSVL9+vWVk5Nzycsba9as0fHjxzV37lyNHDlSN998c4EnyII61BY0vn79+pKk0NBQz4n34teFl4iuxMXN/6dPn9ahQ4cUGxtb4DwxMTHasWNHnqCWe0ktJiZGUsHbdanl5neL9MXLLYqbb75ZkvdJuDB1FGb73nvvPQUGBmr58uUaMmSIUlJSlJSUVOj1REZGavDgwZo3b57279+vFi1aaOLEiZedr3///srKytJ7772nDz/8UC6XS7fddlue6WrVqqUHH3xQixYt0p49e1SlShU9/fTTl1z2W2+9perVq2vBggV5XgMGDNDChQu9ngnjdDqVmpqqWbNmadeuXbrvvvv0n//8x+u5NFeynRUqVFCXLl30wgsv6Mcff9TTTz+tTz75RKtXr5Z0+WMrISFB48aN07p16/Tpp5/ql19+0csvv3zJeVB+EGZQJqxevTrf/znn9hPJvdTRq1cvVahQQZMnT85zYsud38/Pz2tYkjIzMzVr1qw8y69UqVK+zd25z4I5ceKE1/iWLVuqfv36+utf/5rnMol0/mFwf9Srr76qc+fOeYZnz56trKwspaSkFDjPTTfdpMOHD3td6sjKytKMGTMUEhKijh07SpKCg4Ml5d2uSy33q6++0oYNGzzj0tPT9eqrryo2Nvayl/vy0759e3Xt2lWvvvqqFi9enO80Fx8Lhd0+Pz8/ORwOr9aCvXv3atGiRZet6/jx417DISEhatCggdxu92Xnbdq0qRISEjR//nzNnz9ftWrVUocOHTzvZ2dn5znOqlevrqioqEsu/8yZM3r//fd18803q2/fvnlew4cP16lTpzz9yi7ehgoVKngu2eWu50q287fffssz7qqrrvJabkHfGZfLpaysLK9xCQkJqlChQqH2LcoHbs1GmfDQQw8pIyNDvXv3VpMmTZSZmanPP/9c8+fPV2xsrAYPHixJatCggZ544gk99dRTuv7669WnTx8FBARo48aNioqK0tSpU9WuXTtFRERo0KBBGjFihBwOh9544418w1LLli01f/58jR49Wq1bt1ZISIhSU1NVv359hYeH6+WXX1blypVVqVIltW3bVnFxcXrttdeUkpKiZs2aafDgwapdu7Z++eUXrV69WqGhoZ5bj69UZmamunTpon79+mnbtm2aNWuWrrvuOvXo0aPAeYYOHapXXnlFd911lzZv3qzY2Fi9++67+uyzzzR9+nRPP5WgoCDFx8dr/vz5atSokSIjI9W8efMCb4cfM2aM5s2bp5SUFI0YMUKRkZF6/fXXtWfPHr333nt5+rAU1ptvvqlu3bqpV69entaTiIgIHT58WCtXrtS6deu8wltht6979+564YUX1K1bNw0cOFBHjx7VzJkz1aBBg8v2C4mPj1enTp3UsmVLRUZGatOmTZ5bqQujf//+Gj9+vAIDA3X33Xd77ZtTp06pTp066tu3rxITExUSEqKVK1dq48aN+tvf/lbgMpcsWaJTp04V+Nlfc801qlatmt566y31799f99xzj3777TfdcMMNqlOnjn7++WfN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DAAAgK3xcwYAAMDnFOX8XeQ+M6+//rqWLVvmGX7ssccUHh6udu3a6eeffy56tQAAAH9AkcPMM888o6CgIEnShg0bNHPmTE2bNk1Vq1bVww8/XOwFAgAAXEqR+8zs37/f09F30aJFuuWWWzR06FC1b99enTp1Ku76AAAALqnILTMhISE6fvy4JOnjjz9W165dJUmBgYE6c+ZM8VYHAABwGUVumenatavuuece/elPf9L27dt10003SZJ++OEHxcTEFHuBAAAAl1LklpmZM2fq2muv1a+//qr33ntPVapUkSRt3rxZAwYMKPYCAQAALuUP35p96tQpzZs3T6+99po2b97sc08B5tZsAADsp0Rvzc61bt06DRo0SLVq1dJf//pX3XDDDfriiy+udHEAAABXpEh9Zg4fPqy5c+fqX//6l1wul/r16ye3261FixYpPj6+pGoEAAAoUKFbZlJTU9W4cWN9++23mj59ug4ePKgZM2aUZG0AAACXVegw8+GHH+ruu+/WpEmT1L17d/n5+ZVkXZKk7OxsPfnkk4qLi1NQUJDq16+vp556SmX8FxgAAEARFDrMrF+/XqdOnVLLli3Vtm1bvfTSSzp27FhJ1qbnnntOs2fP1ksvvaStW7fqueee07Rp02gRAgAAHoUOM9dcc43++c9/6tChQ7rvvvv0zjvvKCoqSjk5OVqxYoVOnTpV7MV9/vnn6tmzp7p3767Y2Fj17dtXN954o7766qtiXxcAALCnIt/NVKlSJQ0ZMkTr16/Xd999p7/85S969tlnVb16dfXo0aNYi2vXrp1WrVql7du3S5K++eYbrV+/XikpKQXO43a75XK5vF4AAKDsuuJbsyWpcePGmjZtmg4cOKB58+YVV00eY8aM0W233aYmTZqoYsWK+tOf/qRRo0bp9ttvL3CeqVOnKiwszPOKjo4u9roAAIDv+MMPzStJ77zzjh599FE9//zzatasmdLS0jRq1Ci98MILGjRoUL7zuN1uud1uz7DL5VJ0dDQPzQMAwEaK8tA8nw4z0dHRGjNmjIYNG+YZN2XKFL355pv66aefCrUMngAMAID9lMoTgEtDRkaGKlTwLtHPz085OTkWVQQAAHxNkX81uzSlpqbq6aefVt26ddWsWTN9/fXXeuGFFzRkyBCrSwMAAD7Cpy8znTp1Sk8++aQWLlyoo0ePKioqSgMG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1s2aYsuQqVOnqnXr1qpcubKqV6+uXr16adu2bV7TnD17VsOGDVOVKlUUEhKiW265RUeOHLGo4rKhMPu9U6dOeY75+++/v1TqKzdhZv78+Ro9erQmTJigLVu2KDExUcnJyTp69KjVpZVpzZo106FDhzyv9evXW11SmZOenq7ExETNnDkz3/enTZumf/zjH3r55Zf15ZdfqlKlSkpOTtbZs2dLudKy5XL7XZK6devmdfzPmzevFCssm9auXathw4bpiy++0IoVK3Tu3DndeOONSk9P90zz8MMP64MPPtCCBQu0du1aHTx4UH369LGwavsrzH6XpHvvvdfrmJ82bVrpFGjKiTZt2phhw4Z5hrOzs01UVJSZOnWqhVWVbRMmTDCJiYlWl1GuSDILFy70DOfk5JiaNWua559/3jPuxIkTJiAgwMybN8+CCsumi/e7McYMGjTI9OzZ05J6ypOjR48aSWbt2rXGmPPHd8WKFc2CBQs802zdutVIMhs2bLCqzDLn4v1ujDEdO3Y0I0eOtKSectEyk5mZqc2bNyspKckzrkKFCkpKStKGDRssrKzs27Fjh6KiolSvXj3dfvvt2rdvn9UllSt79uzR4cOHvY79sLAwtW3blmO/FKxZs0bVq1dX48aN9cADD+j48eNWl1TmnDx5UpIUGRkpSdq8ebPOnTvndcw3adJEdevW5ZgvRhfv91xvvfWWqlatqubNm2vs2LHKyMgolXrK/A9NStKxY8eUnZ2tGjVqeI2vUaOGfvrpJ4uqKvvatm2ruXPnqnHjxjp06JAmTZqk66+/Xt9//70qV65sdXnlwuHDhyUp32M/9z2UjG7duqlPnz6Ki4vTrl279H//939KSUnRhg0b5OfnZ3V5ZUJOTo5GjRql9u3bq3nz5pLOH/NOp1Ph4eFe03LMF5/89rskDRw4UDExMYqKitK3336rxx9/XNu2bdP7779f4jWVizADa6SkpHj+btGihdq2bauYmBj997//1d13321hZUDJu+222zx/JyQkqEWLFqpfv77WrFmjLl26WFhZ2TFs2DB9//339MUrZQXt96FDh3r+TkhIUK1atdSlSxft2rVL9evXL9GaysVlpqpVq8rPzy9Pb/YjR46oZs2aFlVV/oSHh6tRo0bauXOn1aWUG7nHN8e+9erVq6eqVaty/BeT4cOHa+nSpVq9erXq1KnjGV+zZk1lZmbqxIkTXtNzzBePgvZ7ftq2bStJpXLMl4sw43Q61bJlS61atcozLicnR6tWrdK1115rYWXly+nTp7Vr1y7VqlXL6lLKjbi4ONWsWdPr2He5XPryyy859kvZgQMHdPz4cY7/P8gYo+HDh2vhwoX65JNPFBcX5/V+y5YtVbFiRa9jftu2bdq3bx/H/B9wuf2en7S0NEkqlWO+3FxmGj16tAYNGqRWrVqpTZs2mj59utLT0zV48GCrSyuzHnnkEaWmpiomJkYHDx7UhAkT5OfnpwEDBlhdWply+vRpr//57NmzR2lpaYqMjFTdunU1atQoTZkyRQ0bNlRcXJyefPJJRUVFqVevXtYVXQZcar9HRkZq0qRJuuWWW1SzZk3t2rVLjz32mBo0aKDk5GQLq7a/YcOG6e2339bixYtVuXJlTz+YsLAwBQUFKSwsTHfffbdGjx6tyMhIhYaG6qGHHtK1116ra665xuLq7ety+33Xrl16++23ddNNN6lKlSr69ttv9fDDD6tDhw5q0aJFyRdoyT1UFpkxY4apW7eucTqdpk2bNuaLL76wuqQyrX///qZWrVrG6XSa2rVrm/79+5udO3daXVaZs3r1aiMpz2vQoEHGmPO3Zz/55JOmRo0aJiAgwHTp0sVs27bN2qLLgEvt94yMDHPjjTeaatWqmYoVK5qYmBhz7733msOHD1tdtu3lt88lmTlz5nimOXPmjHnwwQdNRESECQ4ONr179zaHDh2yrugy4HL7fd++faZDhw4mMjLSBAQEmAYNGphHH33UnDx5slTqc/y/IgEAAGypXPSZAQAAZRdhBgAA2BphBgAA2BphBgAA2BphBgAA2BphBgAA2BphBgAA2BphBkCZFxsbq+nTp1tdBoASQpgBYJnDhw9r5MiRatCggQIDA1WjRg21b99es2fPVkZGhtXlAbCJcvPbTAB8y+7du9W+fXuFh4frmWeeUUJCggICAvTdd9/p1VdfVe3atdWjRw+rywRgA7TMALDEgw8+KH9/f23atEn9+vVT06ZNVa9ePfXs2VPLli1TamqqJGnfvn3q2bOnQkJCFBoaqn79+unIkSOe5ezatUs9e/ZUjRo1FBISotatW2vlypUFrtcYo4kTJ6pu3boKCAhQVFSURowYUeLbC6DkEGYAlLrjx4/r448/1rBhw1SpUqV8p3E4HMrJyVHPnj3122+/ae3atVqxYoV2796t/v37e6Y7ffq0brrpJq1atUpff/21unXrptTUVO3bty/f5b733nt68cUX9corr2jHjh1atGiREhISSmQ7AZQOLjMBKHU7d+6UMUaNGzf2Gl+1alWdPXtWkjRs2DAlJSXpu+++0549exQdHS1J+s9//qNmzZpp48aNat26tRITE5WYmOhZxlNPPaWFCxdqyZIlGj58eJ5179u3TzVr1lRSUpIqVqyounXrqk2bNiW4tQBKGi0zAHzGV199pbS0NDVr1kxut1tbt25VdHS0J8hIUnx8vMLDw7V161ZJ51tmHnnkETVt2lTh4eEKCQnR1q1bC2yZufXWW3XmzBnVq1dP9957rxYuXKisrKxS2T4AJYMwA6DUNWjQQA6HQ9u2bfMaX69ePTVo0EBBQUGFXtYjjzyihQsX6plnntGnn36qtLQ0JSQkKDMzM9/po6OjtW3bNs2aNUtBQUF68MEH1aFDB507d+4PbRMA6xBmAJS6KlWqqGvXrnrppZeUnp5e4HRNmzbV/v37tX//fs+4H3/8USdOnFB8fLwk6bPPPtNdd92l3r17KyEhQTVr1tTevXsvuf6goCClpqbqH//4h9asWaMNGzbou+++K5ZtA1D6CDMALDFr1ixlZWWpVatWmj9/vrZu3apt27bpzTff1E8//SQ/Pz8lJSUpISFBt99+u7Zs2aKvvvpKd955pzp27KhWrVpJkho2bKj3339faWlp+uabbzRw4EDl5OQUuN65c+fqX//6l77//nvt3r1bb775poKCghQTE1Namw6gmBFmAFiifv36+vrrr5WUlKSxY8cqMTFRrVq10owZM/TII4/oqaeeksPh0OLFixUREaEOHTooKSlJ9erV0/z58z3LeeGFFxQREaF27dopNTVVycnJuvrqqwtcb3h4uP75z3+qffv2atGihVauXKkPPvhAVapUKY3NBlACHMYYY3URAAAAV4qWGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGuEGQAAYGv/H8KEhNiijlq7AAAAAElFTkSuQmCC",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "#Create a scatter plot using matplotlib where the x-axis is the number of goals and the y-axis is the number of assists for each player. Use different colors to represent players from different teams.\n",
    "football_data.plot(kind='scatter', x='Goals',y='Assists', title='Scatter plot of Goals vs Assists',marker='+')                 \n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8b27c985-26b8-423f-9c66-bde73c88aa5e",
   "metadata": {},
   "source": [
    "# Use numpy to calculate statistical values"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "03d63dd8-bc80-455e-8242-2e53ba7af860",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Mean                  11.933333\n",
      "Median                15.000000\n",
      "standard Deviation     8.438574\n",
      "dtype: float64\n"
     ]
    }
   ],
   "source": [
    "# Use numpy to calculate the mean, median, and standard deviation of the number of goals scored by all players.\n",
    "def stat(grp):\n",
    "    return pd.Series({\n",
    "        'Mean': grp.mean(),\n",
    "        'Median': grp.median(),\n",
    "        'standard Deviation': grp.std()\n",
    "    })\n",
    "statistical_analysis=stat(football_data['Goals'])\n",
    "print(statistical_analysis)"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
