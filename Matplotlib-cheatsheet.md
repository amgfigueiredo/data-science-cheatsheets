# Matplotlib Cheat Sheet

## Introduction

Matplotlib is a Python library used for creating static, animated, and interactive visualizations.

## Installation

```

pip install matplotlib

```

## Importing Matplotlib

```
import matplotlib as mpl
import matplotlib.pyplot as plt
mpl.style.use(['ggplot'])  # Optional: for ggplot-like style
```

## Line Plot

```
plt.plot(x, y)
plt.show()
```

## Figure and Axes

```
fig, ax = plt.subplots()
ax.plot(years, immigrants)
plt.show()
```

## Labels & Titles

```
plt.title('Immigration from Haiti')
plt.xlabel('Years')
plt.ylabel('Number of immigrants')
plt.legend(['Line1', 'Line2'])
plt.grid(True)
plt.show()
```

## Save Figure

```

plt.savefig("plot.png", dpi=300)

```

## Line Styles and Colors

```

plt.plot(x, y, linestyle="--", color="r")

```

## Scatter Plot

```
plt.scatter(x, y, color='b')
plt.show()
```

## Bar Chart

```
plt.bar(group_names, df["horsepower-binned"].value_counts())
df.plot(kind='bar', figsize=(10,6))
plt.show()
```

## Horizontal Bar Chart

```
df.plot(kind='barh', color='red')
plt.show()
```

## Area Chart
```
df.plot(kind='area', alpha=0.25, stacked=False, figsize=(20,10))
plt.show()
```

## Histogram
```
df['2013'].plot(kind='hist', bins=20)
plt.show()
```

## Pie Chart
```
plt.pie(sizes, labels=labels, autopct='%1.1f%%')
plt.show()
```

## Boxplot
```
plt.boxplot(data)
df.plot(kind='box', vert=False)
plt.show()
```

## Subplots
```
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(20,6))
df_CI.plot(kind='box', ax=ax1)
df_CI.plot(kind='line', ax=ax2)
plt.show()
```

## Log Scale

```

plt.yscale("log")

```

## Error Bars
```

plt.errorbar(x, y, yerr=errors, fmt='o')

```

## Heatmap
```
plt.pcolor(df_pivot, cmap='RdBu')
plt.colorbar()
plt.show()
```

## Annotate
```
plt.annotate('', xy=(32, 70), xytext=(28, 20),
             arrowprops=dict(arrowstyle='->', color='blue', lw=2))
```

## Tight Layout

```

plt.tight_layout()

```

## Polynomial Regression

```
def PlotPolly(model, independent_variable, dependent_variable, Name):
    x_new = np.linspace(15, 55, 100)
    y_new = model(x_new)
    plt.plot(independent_variable, dependent_variable, '.', x_new, y_new, '-')
    plt.xlabel(Name)
    plt.ylabel('Price of Cars')
    plt.show()

x = df['highway-mpg']
y = df['price']
f = np.polyfit(x, y, 3)
p = np.poly1d(f)
PlotPolly(p, x, y, 'highway-mpg')
```
