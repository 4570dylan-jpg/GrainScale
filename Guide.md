# Grain Scale – user guide

Grain Scale is a Windows app for rifle load development. It weighs charges on a VEVOR lab scale, keeps your rifles, loads and tests in one place, measures groups from target photos and tells you how sure you can be that one load really is better than another.

Your data lives in **Documents\GrainScale** (the database, a photos folder and automatic backups). Installing, upgrading or uninstalling the app never touches it.

## Getting started

1. **Loads tab:** click **+ Rifle**, then **+ Barrel**, then **+ Load** and fill in the recipe (bullet, powder, primer, charge, CBTO or COAL).
2. Click **+ Test…** on the load. The test wizard sets up the groups for you, for example a charge ladder from 27.6 gr in 0.3 gr steps.
3. **Scale tab:** connect the scale (or tick **Simulate** to try it), click **Open a test…** and weigh each charge. Charges are logged to the test.
4. At the range, print a **Range sheet** from the test to write notes on.
5. Back home, enter or import velocities (**Import Garmin CSV…**) and attach a photo of each target.
6. **Group Analysis tab:** measure each group on its photo, then use **Compare** to see which charge is really best.

Tip: almost everything saves as you type. There's no Save button to forget.

## Scale tab

**Connecting.** Plug in the USB-serial cable, click **↻** to list ports, pick the COM port, keep **9600 baud, None, 8 bits, 1 stop bit**, and click **Connect**. The VEVOR sends grams only; Grain Scale converts to grains. If nothing shows, tick **Show raw scale data** to see exactly what the scale sends, and set the scale's RS232 output to continuous.

**Target and tolerance.** Type the target in grains and pick a tolerance: **Low ±0.1 gr**, **Medium ±0.05 gr**, **High ±0.005 gr** or **Custom**. The big status band shows **UNDER**, **IN TOLERANCE** or **OVER**.

**Stable reading.** A reading counts as stable when it stays within the ± band you set for the number of seconds you set. **Auto-log** logs a charge by itself once it's stable and in tolerance; **Auto-advance** then moves to the next row of the plan.

**Logging.** Press **Space** (or **LOG CHARGE**) to log the current weight. **Shift+Space** logs it even if it's out of tolerance. **Undo last** removes the last one.

**Free weighing vs test mode.** In free weighing nothing is saved to a test. Click **Open a test…** to switch to **TEST MODE**: the plan shows each group's target and quantity, and every charge you log is saved to that group. **Switch test…** and **Close test** do what they say.

**Reports.** Export the logged charges as **Excel (CSV)** or **PDF**, or print them.

## Loads tab: rifles, barrels and loads

The tree on the left goes **Rifle › Barrel › Load › Test**. Use **Search** to filter it, and **Hide rejected / archived loads** to tidy it up. **Duplicate** and **Copy / Move…** work on loads and tests; **Delete** removes the item and everything under it.

**Rifle.** Make, model, action, chambering, stock and optic, plus the rifle's **Brass boxes** (see below).

**Barrel.** Length, twist, chamber, install date and a **round count** that adds up every test plus "Rounds before adding" and "Other rounds (not in tests)". Log **CBTO to lands** whenever you check the throat; loads use the latest measurement for the same bullet to show the jump, so you can watch throat erosion over time.

**Load.** The recipe: bullet (pick from the **Bullet library…** to fill in weight, BC and diameter), powder and lot, primer, brass make, charge, CBTO / COAL and the listed maximum. **Status** is Testing, Proven, Rejected or Archived. Underneath you'll see every result from every test of the load. **Ammo box label…** prints a label.

## Tests and groups

A test is one range session for a load: date, distance, shots per group, conditions and notes, plus a table with one row per **group**.

**The test wizard (+ Test…)** sets up the groups:
- **Charge ladder:** start charge, step and number of groups.
- **Seating depth:** a list of CBTO, COAL or jump values.
- **Same load, several groups:** repeat groups of the load as it is.
- **Component comparison:** one group per primer, powder, brass and so on.

**The groups table.** Type velocities shot by shot. **Enter** moves right across the row and **Ctrl+V** pastes a column of velocities. Group size can be typed in MOA or inches, but measuring the photo (Group Analysis) is more accurate. Click the **Pressure** cell to tick pressure signs. **Fill charges** fills a ladder down the table.

**Photos.** Select a group and use **Attach…**, **Paste** or drag an image onto the photo box. If you shot several groups on one target sheet, choose **All groups in this test** (or **Choose groups**) so the photo is stored once. See *Group Analysis*.

**Other buttons:** **Open in Scale tab** (weigh charges for this test), **Import Garmin CSV…**, **Measure photo**, **New load from this group** (turn the winning group into a new load), **Range sheet** and **Label**.

**Shot or not.** Tests show **○** (not shot yet) or **●** (shot) in the tree and on the test's **Status** line. Click **✔ Mark as shot** after the range trip (see *Brass boxes*). **↶ Undo shot** reverses it.

## Brass boxes

Brass is tracked by **numbered box**, for example **22 ARC #1**. A box belongs to a rifle (action), because the brass gets fire-formed to that chamber.

**Times fired** always means how many times the brass has already been fired. New brass is 0×; factory ammo fired once and then reloaded is 1×.

**Setting up.** On the rifle's page (or a test's **Brass boxes…** button), click **+ Add box**. It's named after the cartridge with the next number. Fill in the make, lot, number of cases and times fired.

**On each test**, pick the **Brass box**. The test records the box's times fired at that moment (it's read-only once a box is chosen) and its **Brass prep** (anneal, size, trim…). Labels and range sheets print it, e.g. "22 ARC #1 (Hornady), 2× fired".

**Mark as shot** counts the rounds the test fired (each group's shots plus foulers and sighters; you can change the number). The box only moves up a firing once all its cases have been fired at the current count, e.g. 15 of 50 leaves the box at 2×; when the total reaches 50 it moves to 3×. Tick **Move the box now** if you reprocess the whole box early. It also asks whether the brass was annealed or trimmed for this loading and records it as "Annealed at 2×".

**Reset box (new brass)** puts new brass in the same box: it starts again at 0× and the old brass goes to the box's **History** with the date and how many firings it lasted. **Retire / restore** hides a box you no longer use.

## Garmin Xero import

Export a session from the Garmin ShotView app as a CSV file. On the test, click **Import Garmin CSV…** (or drop the files on the groups table). Each file fills one group's velocities; check which group each file goes into before clicking **Import**.

Grain Scale shows SD using n−1 (the sample standard deviation). Garmin uses n, so Garmin's SD is slightly lower for the same shots.

## Group Analysis: measuring a group

Pick a test at the top, select a group on the left and use **Measure**.

1. **① Point of aim:** click the centre of the aiming mark.
2. **② Scale:** click two points a known distance apart, such as two grid lines 1" apart, and type that distance in **Scale = … in**.
3. **③ Shots:** click the centre of each bullet hole.

Results show group size (centre to centre) in MOA and inches, **mean radius**, width × height and where the group centre sits against the point of aim. Click **Save size & MR to group** to store them on the test.

**Moving around.** The mouse wheel zooms at the pointer; drag the photo to pan. Drag any mark to adjust it, right-click a shot to delete it, **Undo shot** removes the last one. **✂ Crop** (drag a box) and **⟳ Rotate** change the photo file and move the marks with it.

**Why mean radius?** Group size only uses the two worst shots. Mean radius uses every shot, so it's a steadier measure of precision, especially with small groups.

## Group Analysis: one target sheet, several groups

If you shoot several groups on one sheet (each at its own aiming bull), attach the photo to **all of them** on the test screen. Then:

- Set the **scale once**; every group on the sheet uses it.
- Each group gets **its own point of aim** and shots. The other groups' marks show faded in their own colours so you don't click a hole twice.
- **Next group ▶** moves to the next group, ready for its point of aim.
- **Crop** and **Rotate** move the marks of every group on the sheet.

## Quick measure (loose targets)

To measure a target without creating a test (factory ammo, a friend's rifle, zeroing), click **＋ Quick measure…** or drop / paste (**Ctrl+V**) a photo onto the measuring area. It appears under **★ Loose targets** at the top of the test list.

Set the **Distance** and **Bullet Ø** for it and measure as usual. **Rename…** gives it a name. **Assign to test…** moves the photo and its marks onto a group of a real test (or a new group) if you decide it belongs with a load. **Delete** removes it.

If you drop a photo while a test group without a photo is selected, it's attached to that group instead.

## Overlay and Photos

**Overlay** draws several groups together. Tick the groups on the left.
- **Grid:** all groups on one inch grid, aligned by **point of aim** (shows point-of-impact shifts between charges) or by **group centre** (compares sizes). The table includes all groups combined.
- **On the photo:** the ticked groups drawn on the real target sheet, each with its mean-radius circle.

**Photos** shows every group's picture side by side, cropped to the group, with its size, mean radius and velocity SD. Click one to measure it.

## Compare: how sure can I be?

Compare answers "is this load really better, or was I lucky?".

1. In **Compare** mode, select a group on the left and click **A**, **B**, **C** or **D** to put it in a set, or click **Auto: By charge** (or By seating / By test).
2. The table shows each set's shots, mean radius, average group size and velocity SD. The plot shows every shot around its own group centre.
3. Underneath, each set is compared with the best one, for **precision** and **velocity SD**, e.g. "28.0 gr tighter than 28.5 gr: 86% — leaning. ≈ 6 more shots each for 90%".

**Goal.** Type a goal above the results, e.g. **under 0.50 MOA** for **5-shot groups** (or 3-shot, 10-shot, or mean radius). Each set gets the chance that it really averages under the goal, what it's expected to average, and how many more shots would make it 90% sure. "Averages" matters: a load that averages 0.45 MOA will still print some 0.6 MOA groups.

**Reading the percentage:** below 75% *can't tell yet*; 75–90% *leaning*; 90–95% *likely*; above 95% *confident*.

Rough guide for one group per load (precision):

| Shots per load | 20% tighter | 30% tighter | 50% tighter | 2× tighter |
|---|---|---|---|---|
| 5 | 69% | 76% | 86% | 97% |
| 10 | 78% | 86% | 95% | ~100% |
| 15 (3×5) | 81% | 90% | 97% | ~100% |

So a single 5-shot group only reliably separates loads that are about twice as different. Use ladders to rule out the bad charges, then shoot more on the best two or three.

**Good practice:** measure the photos (a typed-in group size only carries two shots' worth of information and isn't used for precision); shoot the sets on the same day and interleave them (A, B, A, B…).

**Save to test notes** adds the comparison, dated, to the test's notes; **Copy** puts it on the clipboard.

## Charts

Pick a test (or **All tests of this load**):
- **Velocity vs charge:** average velocity with min–max bars and the fps per grain between steps. Look for flat spots.
- **SD & ES:** per group; the lowest SD is highlighted.
- **Group size:** group size and mean radius per group, in MOA; the smallest is highlighted.

The table underneath has all the numbers.

## Labels and range sheets

**Range sheet** (on a test) prints the recipe, brass, conditions and a table per group to take to the range.

**Label** prints ammo box labels on Avery sheets: one label for the whole test, one per group, or just the selected group. **Skip used labels** lets you reuse a partly used sheet. Check the first print on plain paper against the sheet.

## Backups and databases

Every time you close Grain Scale, it zips the database and photos into **Documents\GrainScale\backups**, keeping the last 10. It skips this if nothing changed.

**File → Back up (zip)…** makes a backup wherever you like. To restore, unzip it and use **File → Open database…** on the .db file.

**File → Open database… / New database…** switch to another database (for example a separate one for a second shooter). The app remembers the last one. **Open data folder** opens the folder in Explorer.
