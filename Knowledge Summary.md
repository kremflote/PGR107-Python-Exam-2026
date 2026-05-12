


<font color="#c0504d">Lecture 11 - Matplotlib legends and subplot layouts:</font>
**P11.1.ipynb — Customizing Plot Legends**
This notebook covers how to add and style legends on matplotlib plots. 
- **6.1** – Basic legend with `ax.legend()`, plotting sine and cosine curves with labels
- **6.2** – Controlling legend position with `loc=` and toggling the frame with `frameon=`
- **6.3** – Multi-column legends using `ncol=2`
- **6.4** – Placing two separate legends on the same axes using `matplotlib.legend.Legend` and `ax.add_artist()`
Libraries used: `matplotlib.pyplot`, `matplotlib.legend.Legend`, `numpy` 
Key methods: `ax.plot()`, `ax.legend()`, `ax.axis()`, `ax.add_artist()`, `np.linspace()`, `np.sin()`, `np.cos()`

**P11.2.ipynb — Multiple Subplots**
This notebook covers the different ways to create and arrange multiple subplots in a single figure:
- Creating overlapping/inset axes with `plt.axes([x, y, width, height])`
- Using `fig.add_axes()` for manual placement
- Using `fig.add_subplot()` with 3-digit shorthand (e.g. `211`, `122`) for grid layouts
- Looping with `plt.subplot(rows, cols, i)` to create a 2×3 grid
- Controlling spacing between subplots with `fig.subplots_adjust(hspace=, wspace=)`
Libraries used: `matplotlib.pyplot`, `numpy` Key methods: `plt.axes()`, `fig.add_axes()`, `fig.add_subplot()`, `plt.subplot()`, `fig.subplots_adjust()`, `np.linspace()`, `np.sin()`, `np.cos()`

**lec11.1 — Simple Scatter Plots**
Covers how to create scatter plots using `plt.plot()` with various marker types. Builds up from a basic red `+` marker plot to a showcase of all common marker styles, then adds line+marker combos and full styling with `markersize`, `markerfacecolor`, `markeredgecolor`, and `linewidth`.

Libraries: `matplotlib.pyplot`, `numpy` Key methods: `plt.plot()`, `plt.legend()`, `plt.xlim()`, `plt.ylim()`, `np.linspace()`, `np.sin()`, `rng.rand()`

---

**lec11.2 — Line Plots, Styles & Labels**
Covers the fundamentals of line plots: applying styles with `plt.style.use()`, saving figures with `savefig()`, controlling line color and style (named, shorthand, grayscale), setting axis limits, and adding titles/axis labels. Ends with using `ax.set()` to configure everything in one call.

Libraries: `matplotlib.pyplot`, `numpy` Key methods: `plt.style.use()`, `fig.savefig()`, `plt.plot()`, `plt.xlim/ylim()`, `plt.title/xlabel/ylabel()`, `plt.legend()`, `ax.set()`

---

**lec11.3 — Visualizing Errors**
Short but focused notebook on error bars. Plots noisy sine data and adds vertical error bars using `plt.errorbar()`, with styling options for error line color, width, and cap size.

Libraries: `matplotlib.pyplot`, `numpy` Key methods: `plt.errorbar()`, `np.random.randn()`, `np.linspace()`, `np.sin()`

---

**lec11.4 — Density and Contour Plots**
Covers 3D-to-2D visualization using contour plots. Defines a custom function `f(x, y)`, builds a 2D grid with `np.meshgrid()`, and plots it with `plt.contour()` — first in plain black, then color-coded using the `RdGy` colormap with 20 contour levels.

Libraries: `matplotlib.pyplot`, `numpy` Key methods: `np.meshgrid()`, `np.linspace()`, `plt.contour()`, `cmap=` argument

---

**lec11.5 — Histograms**
Covers creating histograms from random normal data. Progresses from a basic `plt.hist()` call to customizing bins, color, alpha transparency, and `histtype`. Also demonstrates overlapping multiple histograms using `**kwargs` to pass shared styling, and explores how alpha blending looks with different distributions.

Libraries: `matplotlib.pyplot`, `numpy` Key methods: `plt.hist()`, `np.random.randn()`, `np.random.normal()`, `**kwargs` pattern


<font color="#c0504d">Lecture 10: Introduction to Pandas Data Structures</font>

**lec10.pdf — Python in Data Science: Pandas Objects**

16 pages introducing the Pandas library and its three core data structures. More conceptual/theoretical than the lec11 slides — focuses on _what_ these structures are and _how to think about them_ rather than extensive coding examples.

---

**1.1 Series** — A one-dimensional indexed array. Contrasts it with NumPy arrays (implicit integer index) vs. Pandas Series (explicit, flexible index — can be strings, floats, etc.). Frames a Series as a _typed dictionary_: maps typed keys to typed values, making it more efficient than plain Python dicts. Covers construction via `pd.Series(data, index=index)` where data can be a list, NumPy array, scalar, or dictionary.

**1.2 DataFrame** — A two-dimensional structure, framed two ways: as a _generalized NumPy array_ (flexible row and column labels) and as a _specialized dictionary_ (maps column names to Series). Covers multiple construction methods: from a single Series, list of dicts, 2D NumPy array, or NumPy structured array.

**1.3 Index** — Briefly introduces the Index object as both an immutable array and an ordered set.

---

Library: `pandas` Key concepts: `pd.Series`, `pd.DataFrame`, `pd.Index`, indexing, construction patterns

<font color="#c0504d">Lecture 9 — Pandas Series, DataFrames, and Data Operations</font>

**lec9.1_Series1.ipynb** 
Deep dive into the Pandas `Series` object. Starts with basic creation and `.values`/`.index` attributes, then covers custom string and non-sequential integer indexes. Highlights the `iloc` vs `loc` distinction when indexes are non-default integers — a common source of confusion. Builds a real population dataset (US states + Oslo + Beijing) as a Series from a dictionary, demonstrating slicing on string-indexed data. Ends with three Series construction patterns: from list, from scalar with index, and from dict with selective index.

Libraries: `numpy`, `pandas` Key methods: `pd.Series()`, `.values`, `.index`, `.ndim`, `.shape`, `.iloc[]`, `.loc[]`, slicing

---

**9.2 (1).ipynb — Operating on Data in Pandas**

Covers how NumPy ufuncs and arithmetic operations work on Pandas objects. Shows that ufuncs like `np.exp()` apply element-wise to both Series and DataFrames. Key focus is **index alignment** — when adding two Series/DataFrames with different indexes, Pandas aligns on index and fills missing overlaps with `NaN`. Demonstrates `fill_value=0` as a fix. Includes a worked DataFrame example with mismatched columns and rows.

Libraries: `numpy`, `pandas` Key methods: `np.exp()`, `A + B`, `A.add(B)`, `A.add(B, fill_value=0)`

---

**P9.1.ipynb — Exercise: NumPy**

A practice exercise (no solution code, just task descriptions). Tasks involve building 3×3 matrices manually and with `arange`, then performing element-wise power operations, modifying values, boolean filtering, slicing for even/odd numbers, and combining arrays.

Libraries: `numpy` Key methods: `np.array()`, `np.arange()`, slicing, boolean indexing, `np.append()`

---

**P9.2.ipynb — Exercise: Pandas DataFrame**

A practice exercise on DataFrames using Norwegian city data (Oslo, Bergen, Stavanger, Trondheim). Tasks cover converting a dict to DataFrame, column selection, row selection, boolean filtering, adding a computed column (population density), finding the max, and computing averages.

Libraries: `pandas` Key methods: `pd.DataFrame()`, column/row selection, boolean filtering, `.max()`, `.mean()`

<font color="#c0504d">Lecture 8 — NumPy Universal Functions, Transposition, and Broadcasting</font>

**lec8.1_ufunc.ipynb — Universal Functions (ufuncs)**

Starts with a recap of NumPy arrays: shape, ndim, reshape, and the `np.newaxis` trick for adding dimensions. Then covers ufuncs — fast element-wise operations on arrays. Demonstrates arithmetic ufuncs (`+`, `-`, `*`, `/`, `**`, `%`), math functions (`np.sqrt`, `np.exp`, `np.power`, `np.maximum`), and aggregation functions (`np.sum`, `np.mean`, `np.where`, `.sum(axis=)`, `.mean(axis=)`). Includes a `timeit` comparison to show ufunc speed.

Libraries: `numpy`, `timeit` Key methods: `np.sqrt()`, `np.exp()`, `np.power()`, `np.maximum()`, `np.where()`, `np.sum()`, `np.mean()`, `np.cumsum()`, `.sum(axis=)`, `np.newaxis`

---

**lec8.2.ipynb — Transposing Arrays and Swapping Axes**

Covers array transposition with `.T` and `.transpose()`. Shows using `np.dot()` and `np.matmul()` for matrix multiplication on transposed arrays. Extends to 3D arrays and reordering axes with `.transpose((1, 0, 2))`.

Libraries: `numpy` Key methods: `.T`, `.transpose()`, `np.dot()`, `np.matmul()`, `.reshape()`

---

**lec8.3.ipynb — Broadcasting**

Deep dive into NumPy broadcasting — how operations work between arrays of different shapes. Covers the three broadcasting rules explicitly: (1) padding shapes with 1s on the left, (2) stretching dimensions of size 1, (3) raising an error when shapes are incompatible. Uses `np.newaxis` to reshape for column-wise broadcasting. Ends with a brief visual demo using `plt.imshow()` to display the result of a broadcasted operation as a grayscale image.

Libraries: `numpy`, `matplotlib.pyplot` Key methods: `np.arange()`, `np.ones()`, `np.newaxis`, `.reshape()`, `plt.imshow()`, `plt.colorbar()`

---

**P8.ipynb — Exercise: NumPy Operations**

Practice tasks covering all three lecture topics: element-wise arithmetic on 1D arrays, ufunc aggregations (`sum`, `prod`, `cumsum`), and broadcasting with 2D and 3D arrays including `reshape(-1, 1)` for column broadcasting.

---

**P8_Solution.ipynb — Exercise Solutions**

Complete solutions for all P8 tasks. Useful for reference — shows clean, concise NumPy patterns including `np.copy()` for safe array duplication and `reshape(-1, 1)` for broadcasting.

<font color="#c0504d">Lecture 7 — Introduction to NumPy: Arrays, Indexing, and Arithmetics</font>

Here's the full breakdown of Lecture 7:

---

**lec7_1.ipynb — NumPy Arrays: Basics and Arithmetic**

Introduces NumPy arrays from the ground up. Covers creating arrays with `np.array()`, inspecting `.ndim`, `.shape`, and element access patterns (`arr[i]`, `arr[i,j]`). Demonstrates array creation functions: `np.zeros()`, `np.zeros_like()`, `np.eye()`, `np.arange()`. Covers data types and `dtype=` argument, and casting between types with `.astype()`. Includes a `timeit` benchmark comparing Python lists vs NumPy arrays for arithmetic — demonstrating vectorization speed. Ends with element-wise comparison operators (`arr2 > arr`).

Libraries: `numpy`, `timeit` Key methods: `np.array()`, `np.zeros()`, `np.zeros_like()`, `np.eye()`, `np.arange()`, `.astype()`, `.ndim`, `.shape`, `timeit`

---

**lec7.2.ipynb — Indexing, Slicing, Boolean and Fancy Indexing**

Covers all major ways to select data from NumPy arrays. Starts with 1D slicing and the important "view vs copy" concept — slices are views, so modifying them changes the original array. Extends to 2D and 3D indexing with both `arr[i][j]` and `arr[i, j]` notation. Covers 2D slicing, boolean indexing (using masks, `~`, `|`), and fancy indexing (selecting rows by list of indices, both positive and negative). Ends with transposition (`.T`, `.transpose()`) and matrix multiplication (`np.dot`, `np.matmul`) — overlapping with lec8.2.

Libraries: `numpy` Key methods: `.copy()`, slicing, `names == 'Bob'`, `~cond`, `mask = ... | ...`, `arr[[4,3,0]]`, `.T`, `.transpose()`, `np.dot()`, `np.matmul()`

---

**P7.1.ipynb — Group Exercise / Mini-Project Discussion**

Not a coding notebook — this is a class activity. Students finish Mini-Project 1 group work and discuss a Norwegian education statistics dataset from udir.no, defining a Python project problem from it. No code content.

---

**PGR107-lec7.pdf — Lecture Slides**

23 pages covering the same ground as the notebooks, with added conceptual framing: NumPy's purpose (vectorized ops, no loops, linear algebra, Fourier transforms), ndarray properties (homogeneous type, shape/dtype), a full dtype reference table, and the concept of vectorization. Visually illustrates 2D/3D indexing, slicing, boolean indexing, and fancy indexing with diagrams. Mostly aligns with the notebooks — no major new topics beyond what's coded.

<font color="#c0504d">Lecture 6 — Python Data Structures: Tuples, Lists, Dicts, and Functions</font>

**Lec6.1_tuple_list.ipynb — Tuples and Lists**

Covers the two most fundamental Python sequence types. For tuples: immutability (you can't reassign elements, but mutable contents like lists inside can still be modified), concatenation with `+`, and repetition with `*`. For lists: creation, modifying elements in-place, `append`, `insert`, `pop`, `remove`, membership testing with `in`, concatenation with `+` vs `extend`, and step slicing with `[::2]`.

Key methods: `tuple()`, `list()`, `.append()`, `.insert()`, `.pop()`, `.remove()`, `.extend()`, slicing

---

**lec6.2_dict.ipynb — Dictionaries, zip, Lambda, and Namespaces**

The main lecture notebook. Covers dicts thoroughly: creation, access, insertion, deletion (`del`, `.pop()`), `.keys()`, `.values()`, `.items()`, `.update()`, and iterating with `for key, value in d.items()`. Introduces `zip()` to pair two lists, and `enumerate()` for indexed iteration. Includes a practical grouping-by-first-letter example. Covers namespaces and the `global` keyword, returning multiple values from a function via a dict, and lambda functions used with a custom `apply_to_list()` helper.

Key methods: `zip()`, `enumerate()`, `.items()`, `.keys()`, `.values()`, `.update()`, `.pop()`, `del`, `global`, `lambda`

---

**P6.1_instructions.ipynb — Group Exercise Instructions**

No code — a class activity prompt. Students work in groups to research and understand `zip`, unzip, and lambda functions, then write original code to demonstrate their understanding.

---

**P6.2_zip_iteration.ipynb — Practice: zip, Lambda, List Comprehensions**

Short practice notebook. Builds a dict and list of tuples from two lists using `zip`. Demonstrates lambda via `apply_to_list()`. Shows list comprehensions with arithmetic transformations, including converting strings to ints mid-comprehension.

Key methods: `zip()`, `lambda`, list comprehensions, `int()`

---

**P6.3_zip_unzip.ipynb — Practice: zip and unzip**

Focused single-topic notebook. Zips two lists together, then unzips using `zip(*zipped)` — demonstrating the unpacking operator `*` as the inverse of zip.

Key methods: `zip()`, `zip(*zipped)`, `list()`

---

**PGR107_Lec6.pdf — Lecture Slides**

18 pages. Covers the same content as the notebooks plus one topic not in any notebook: **Sets** — described as unordered collections of unique elements (like dicts but keys only, no values). Also explicitly contrasts `insert` vs `append` performance, and `+` vs `extend` for list concatenation. Otherwise aligns with the notebooks.

New topic not in notebooks: **Sets** (`set`, unordered, unique elements)