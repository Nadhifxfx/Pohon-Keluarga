# Semantic Network Pohon Keluarga

**Soal :**<br>
•	Buatlah progam python untuk Representasi Pengetahuan di bawah ini<br>
•	Dengan relasi orang tua, saudara laki2, saudara Perempuan, paman, bibi, kakek, nenek dan sepupu.<br> 

![image](https://github.com/user-attachments/assets/fd42e616-449a-455d-9d37-b6116a5584c2)

 # Jawaban

```python
import networkx as nx
import matplotlib.pyplot as plt

# Membuat graf kosong
G = nx.DiGraph()

# Menambahkan node (anggota keluarga) dan relasi (edges)
relationships = [
    ("Hadi", "Desi", "orang tua"),
    ("Hadi", "Wahyu", "orang tua"),
    ("Hadi", "Rina", "orang tua"),
    ("Hadi", "Ardi", "orang tua"),
    ("Ferdie", "Desi", "orang tua"),
    ("Ferdie", "Wahyu", "orang tua"),
    ("Ferdie", "Rina", "orang tua"),
    ("Ferdie", "Ardi", "orang tua"),
    ("Bayu", "Tari", "orang tua"),
    ("Bayu", "Desi", "pasangan"),
    ("Fahrul", "Tari", "pasangan"),
    ("Fahrul", "Wanda", "orang tua"),
    ("Desi", "Tari", "orang tua"),
    ("Tari", "Wanda", "orang tua"),
    ("Desi", "Nurul", "orang tua"),
    ("Desi", "Yanto", "orang tua"),
    ("Rina", "Hamzah", "orang tua"),
    ("Nurul", "Aji", "orang tua"),
    ("Nurul", "Gunawan", "orang tua"),
    ("Ardi", "Eka", "orang tua"),
    ("Ardi", "Mira", "orang tua"),
    ("Ardi", "Bastian", "orang tua"),
    ("Arya", "Eka", "orang tua"),
    ("Arya", "Mira", "orang tua"),
    ("Arya", "Bastian", "orang tua"),
    ("Mira", "Anggun", "orang tua"),
    ("Mira", "Boy", "orang tua"),
    ("Arya", "Ardi", "pasangan")
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
nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels, font_size=8, font_color="green")

plt.title("Jaringan Semantik Pohon Keluarga (Posisi Manual)")
plt.show()
```
**Output :** <br>
![image](https://github.com/user-attachments/assets/db0572f1-28d8-4315-adbf-fcbf682b0839)


