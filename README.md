# Semantic Network Pohon Keluarga

**Soal :**<br>
•	Tulislah Representasi Pengetahuan dari pohon keluarga diatas. Dengan relasi orang tua, saudara laki2, saudara Perempuan, paman, bibi, kakek, nenek dan sepupu.<br> 
•	Buatlah progam python untuk Representasi Pengetahuan di bawah ini<br>

![image](https://github.com/user-attachments/assets/fd42e616-449a-455d-9d37-b6116a5584c2)



 # Jawaban

```python
import networkx as nx
import matplotlib.pyplot as plt

# Membuat graf kosong
G = nx.DiGraph()

# Menambahkan node (anggota keluarga) dan relasi (edges)
relationships = [
    ("Hadi", "Fathur", "orang tua"),
    ("Hadi", "Wahyu", "orang tua"),
    ("Hadi", "Rina", "orang tua"),
    ("Hadi", "Ardi", "orang tua"),
    ("Nadhif", "Fathur", "orang tua"),
    ("Nadhif", "Wahyu", "orang tua"),
    ("Nadhif", "Rina", "orang tua"),
    ("Nadhif", "Ardi", "orang tua"),
    ("Bayu", "Tari", "orang tua"),
    ("Bayu", "Fathur", "pasangan"),
    ("Fahrul", "Tari", "pasangan"),
    ("Fahrul", "Wanda", "orang tua"),
    ("Fathur", "Tari", "orang tua"),
    ("Tari", "Wanda", "orang tua"),
    ("Fathur", "Nurul", "orang tua"),
    ("Fathur", "Yanto", "orang tua"),
    ("Rina", "Hamzah", "orang tua"),
    ("Nurul", "Aji", "orang tua"),
    ("Nurul", "Gunawan", "orang tua"),
    ("Ardi", "Eka", "orang tua"),
    ("Ardi", "Mira", "orang tua"),
    ("Ardi", "Bastian", "orang tua"),
    ("Ana", "Eka", "orang tua"),
    ("Ana", "Mira", "orang tua"),
    ("Ana", "Bastian", "orang tua"),
    ("Mira", "Anggun", "orang tua"),
    ("Mira", "Boy", "orang tua"),
    ("Ana", "Ardi", "pasangan")
]

# Menambahkan edges ke graf berdasarkan relasi
for parent, child, relation in relationships:
    G.add_edge(parent, child, relationship=relation)

# Mengatur posisi node secara manual
pos = {
    "Hadi": (0, 6),
    "Nadhif": (2, 6),
    "Bayu": (-3, 4),
    "Wahyu": (0, 4),
    "Rina": (2, 4),
    "Ardi": (4, 4),
    "Fathur": (-1, 4),
    "Fahrul": (-4, 2),
    "Tari": (-2, 2),
    "Wanda": (-2, 0),
    "Nurul": (-1, 2),
    "Yanto": (0, 2),
    "Hamzah": (2, 2),
    "Aji": (-1, 0),
    "Gunawan": (0, 0),
    "Eka": (3, 2),
    "Mira": (5, 2),
    "Bastian": (6, 2),
    "Ana": (5, 4),
    "Anggun": (5, 0),
    "Boy": (6, 0)
}

# Menggambar graf
plt.figure(figsize=(16, 10))

# Menampilkan node dan edge
nx.draw(G, pos, with_labels=True, node_size=2000, node_color="skyblue", font_size=10, font_color="black", font_weight="bold", arrowsize=20)

# Menambahkan label untuk jenis hubungan pada edges
edge_labels = nx.get_edge_attributes(G, 'relationship')
nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels, font_size=8)

plt.title("Jaringan Semantik Pohon Keluarga (Posisi Manual)")
plt.show()


```
**Output :** <br>
![image](https://github.com/user-attachments/assets/344c16a2-4df6-4a14-9670-86ce16ea9927)

