# Assignment-1


import matplotlib.pyplot as plt
import numpy as np

# Data
months = ["07/2019", "08/2019", "09/2019", "10/2019", "11/2019"]
searches = [50, 53, 59, 56, 62]
direct = [39, 47, 42, 51, 51]
social_media = [70, 80, 90, 87, 92]

x = np.arange(len(months))
width = 0.25  # width of bars

# Plot
fig, ax = plt.subplots(figsize=(8,6))
rects1 = ax.bar(x - width, searches, width, label='Searches', color='skyblue')
rects2 = ax.bar(x, direct, width, label='Direct', color='pink')
rects3 = ax.bar(x + width, social_media, width, label='Social Media', color='orange')

# Labels
ax.set_xlabel("Months")
ax.set_ylabel("Visitors in thousands")
ax.set_title("Visitors by web traffic sources")
ax.set_xticks(x)
ax.set_xticklabels(months)
ax.legend()

# Add bar labels
for rects in [rects1, rects2, rects3]:
    for rect in rects:
        height = rect.get_height()
        ax.text(rect.get_x() + rect.get_width()/2., height + 1,
                '%d' % int(height),
                ha='center', va='bottom')

plt.tight_layout()
plt.show()



