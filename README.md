# FreeCAD_ExportToOrca
FreeCAD macro to export directly to OrcaSlicer

## What It Does

Exports the currently selected objects from FreeCAD as a timestamped STEP file to a local folder and immediately opens the file in OrcaSlicer.

---

## Configuration

Before using the macro, open the `ExportToOrca` file and adjust the two paths at the top to match your system:

```python
# Fixed export folder — must exist or will be created automatically
EXPORT_FOLDER = r"C:\Temp\orca_export"

# Full path to the OrcaSlicer executable
ORCA_PATH = r"C:\Program Files\OrcaSlicer\orca-slicer.exe"
```

---

## Step 1 — Install the Macro

1. Find FreeCAD's **Macro folder**:
   - **Windows:** `%APPDATA%\FreeCAD\Macro\`  
     (paste this path into File Explorer's address bar to open it)
   - **Linux:** `~/.FreeCAD/Macro/`
   - **macOS:** `~/Library/Application Support/FreeCAD/Macro/`

2. Copy the `ExportToOrca` file from this repository into that folder and rename it `ExportToOrca.FCMacro`.

---

## Step 2 — Verify the Macro Is Recognised

1. Open FreeCAD.
2. Go to **Macro → Macros…** (or **Tools → Macros…** depending on your FreeCAD version).
3. In the dialog that opens, confirm that **ExportToOrca** appears in the list.
4. Close the dialog.

---

## Step 3 — Add a Toolbar Button

1. In FreeCAD, open **Tools → Customize…**

2. Click the **Toolbars** tab.

3. In the **Workbench** dropdown on the right-hand side, choose the workbench where you want the button to appear (e.g. *Part Design*, *Part*, or *Global* to make it available everywhere).

4. Click **New…** to create a new custom toolbar, give it a name (e.g. `Export`), and click **OK**.  
   *(Alternatively, select an existing toolbar to add the button to it.)*

5. In the **Category** dropdown on the left-hand side, select **Macros**.

6. Your macro (**ExportToOrca**) should appear in the commands list below. Select it.

7. Click the **→** (right arrow) button between the two panels to add the macro to your toolbar.

8. *(Optional)* To assign a custom icon or tooltip, select the macro entry in the right-hand panel and click **Change icon…** or edit the **Button text** / **Tooltip** fields.

9. Click **OK** to save the changes. The new toolbar will appear in the FreeCAD workspace.

---

## Usage

1. Open a FreeCAD document and select one or more objects you want to export.
2. Click your new toolbar button (or run the macro via **Macro → Macros…**).
3. The macro will:
   - Delete any existing `.step` files in `EXPORT_FOLDER` (automatic cleanup).
   - Export the selection as a new timestamped STEP file.
   - Launch OrcaSlicer with the exported file.

Status messages are printed to the **Report View** panel (`View → Panels → Report View`).
