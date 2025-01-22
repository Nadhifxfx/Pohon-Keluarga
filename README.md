# Semantic Network Pohon Keluarga

**Soal :**
•	Tulislah Representasi Pengetahuan dari pohon keluarga diatas. Dengan relasi orang tua, saudara laki2, saudara Perempuan, paman, bibi, kakek, nenek dan sepupu. Menggunakan pohon 1. 
•	Buatlah progam python untuk Representasi Pengetahuan di bawah ini
![image](https://github.com/user-attachments/assets/fd42e616-449a-455d-9d37-b6116a5584c2)



 # Jawaban

```python
import networkx as nx
import matplotlib.pyplot as plt

# Membuat graf kosong
G = nx.DiGraph()

# Menambahkan node (anggota keluarga) dan relasi (edges)
relationships = [
    ("Hadi", "Desi", "parent"),
    ("Hadi", "Wahyu", "parent"),
    ("Hadi", "Rina", "parent"),
    ("Hadi", "Ardi", "parent"),
    ("Ferdie", "Desi", "parent"),
    ("Ferdie", "Wahyu", "parent"),
    ("Ferdie", "Rina", "parent"),
    ("Ferdie", "Ardi", "parent"),
    ("Bayu", "Tari", "parent"),
    ("Bayu", "Desi", "Pasangan"),
    ("Fahrul", "Tari", "Pasangan"),
    ("Fahrul", "Wanda", "parent"),
    ("Desi", "Tari", "parent"),
    ("Tari", "Wanda", "parent"),
    ("Desi", "Nurul", "parent"),
    ("Desi", "Yanto", "parent"),
    ("Rina", "Hamzah", "parent"),
    ("Nurul", "Aji", "parent"),
    ("Nurul", "Gunawan", "parent"),
    ("Ardi", "Eka", "parent"),
    ("Ardi", "Mira", "parent"),
    ("Ardi", "Bastian", "parent"),
    ("Arya", "Eka", "parent"),
    ("Arya", "Mira", "parent"),
    ("Arya", "Bastian", "parent"),
    ("Mira", "Anggun", "parent"),
    ("Mira", "Boy", "parent"),
    ("Arya", "Ardi", "Pasangan")
]

# Menambahkan edges ke graf berdasarkan relasi
for parent, child, relation in relationships:
    G.add_edge(parent, child, relationship=relation)

# Mengatur posisi node secara manual
pos = {
    "Hadi": (0, 6),
    "Ferdie": (2, 6),
    "Bayu": (-3, 4),
    "Wahyu": (0, 4),
    "Rina": (2, 4),
    "Ardi": (4, 4),
    "Desi": (-1, 4),
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
    "Arya": (5, 4),
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
