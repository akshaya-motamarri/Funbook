# 🎨 Color Palette Extractor

## The story behind this

I'm a Pinterest fanatic. You know how it goes - you see a home decor picture or an outfit flat lay and something about it just *looks right*. So I screenshot it. Then open the color picker on my iPhone. One by one. Getting the EXACT color because apparently I have a perfectionist disease.

Back in college, K-Means was always taught for customer segmentation. Group people by behaviour, find the centre of each group. Honestly? Never excited me enough to actually use it.

Until I was clearing out my wardrobe and needed a color palette to shop efficiently.

**What if I fed it pixels instead of customers?**

K-Means didn't care. It just needs data points. I gave it millions of them (one per pixel). It found the dominant color families. Each family's centre = the dominant color.

Same algorithm. Different data. Completely different world.

---

## What does this do?

Takes any image → finds dominant colors using K-Means clustering → gives each color a name → scores how harmonious the palette is.

**Under the hood:**
- Loads the image and converts it into a giant table of numbers (one row per pixel, three columns for R, G, B)
- Filters out grey/neutral background pixels so they don't drown out the real colors
- Runs K-Means to group all pixels into N color families
- The center of each family = the most representative color
- Finds the closest CSS3 color name for each hex code
- Scores harmony using Euclidean distance between colors (like a dartboard — closer colors = higher score)

---

## Tech stack

- **Python**
- **Pillow (PIL)** — opens and reads images
- **NumPy** — converts image to array of pixel values
- **Pandas** — filters out background noise before clustering
- **Scikit-learn** — K-Means clustering (same library used for ML models)
- **Matplotlib** — draws the color palette visualization
- **WebColors** — maps hex codes to color names
- **SciPy** — Euclidean distance for harmony scoring

---

## How to run

```bash
pip install pillow numpy pandas scikit-learn matplotlib webcolors scipy requests
```

1. Clone this repo
2. Open `Color_Palette_Extractor.ipynb` in Jupyter or VS Code
3. Update the image path in Step 2 (or use a direct .jpg/.png URL)
4. Run all cells
5. Your palette is saved as `palette_named.png`

**Note:** Instagram and Pinterest page links won't work directly — save the image to your computer first and load it locally.

---

## Sample output

*(Your palette image here)*

---

## Coming soon

- Streamlit interface so anyone can drag and drop their own image
- Style classification (Minimalist / Moody / Warm / Cool)
- Compare palettes across multiple images
- Full Brand Aesthetics Analyzer for Instagram feeds

---

## Author

Akshaya Motamarri | Data Science Consultant | Wells Fargo  
