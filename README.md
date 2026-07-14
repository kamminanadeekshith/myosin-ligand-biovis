# Structural Visualization and Interaction Kinematics of Scallop Myosin (1B7T)

An interdisciplinary bioinformatics project combining **structural biology modeling** and **data visualization** to analyze the interaction kinetics and binding affinities of scallop Myosin with essential cellular co-factors.

---

## 👥 Contributor
* **K. Deekshith** &mdash;

---

## 🧬 Biological Context & Target Profile
* **Target Protein:** Myosin (PDB ID: `1B7T`)[cite: 1]
* **Source Organism:** *Argopecten irradians* (Commonly known as the Bay Scallop)[cite: 1]
* **Target Ligands / Co-factors:** Adenosine-5'-Diphosphate (ADP), Calcium ($Ca^{2+}$), and Magnesium ($Mg^{2+}$)[cite: 1]
* **Functional Significance:** Myosin acts as a crucial motor protein that interacts with actin filaments to facilitate muscle contraction[cite: 1]. This structural analysis provides insights into locomotion efficiency, marine adaptation, and evolutionary muscle fiber specialization within marine environments[cite: 1].

---

## 🎬 1. Molecular Interaction Animation (PyMOL)
We utilized PyMOL to reconstruct the 3D crystal structure of Myosin and map its native binding pocket regions[cite: 1]. By interpolating localized atom selections and tracking coordinate paths across frame states, we simulated camera movements to highlight the structural orientation of target ligands[cite: 1, 2].

### Interaction Sequence Loop
![Myosin Frame Loop](./outputs/myosin_interaction.gif)
*(Note: Ensure your rendered .gif file is saved in the `outputs/` folder to show up here)*

### Automation Workflow Syntax (`scripts/generate_scene.pml`)
The animation timeline was programmatically handled using the following command-line interface logic[cite: 1]:
```txt
fetch 1B7T, type=pdb, async=0
select ligand_adp, resn ADP
cmd.orient("ligand_adp", animate=-1)
util.cba(33, "1B7T")
mset 1x1800
mview store, 1
turn y, 180
mview store, 200
turn y, 180
mview store, 550
mplay
