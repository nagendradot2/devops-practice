md

📘 RDS Snapshot and Restore – Step-by-Step Guide
📌 Task Overview

The objective of this task is to:

Create a snapshot of an existing RDS instance
Restore the snapshot into a new RDS instance
Ensure the new instance uses the correct configuration
Verify the restored instance is available
🧾 Prerequisites
Existing RDS instance: nautilus-rds
Instance must be in Available state before taking snapshot
📸 Step 1: Take RDS Snapshot
Login to AWS Console

Navigate to:

RDS → Snapshots
Click on Take snapshot
Configure:
Snapshot type: DB instance
DB instance: nautilus-rds
Snapshot name: nautilus-snapshot
Click Take snapshot

📷 Example:

🔄 Step 2: Restore Snapshot to New Instance

Go to:

RDS → Snapshots
Select snapshot: nautilus-snapshot
Click Actions → Restore snapshot
⚙️ Step 3: Configure New RDS Instance

While restoring, configure:

DB instance identifier:

nautilus-snapshot-restore

DB instance class:

db.t3.micro
Keep other settings as default (unless specified)
Click Restore DB instance
⏳ Step 4: Wait for Completion

Navigate to:

RDS → Databases

Wait until status becomes:

Available
✅ Step 5: Verification

Ensure the following:

Parameter	Expected Value
Instance Name	nautilus-snapshot-restore
Status	Available
Instance Class	db.t3.micro

📷 Example:

⚠️ Notes
Snapshot acts as a backup of the database
Restore operation creates a new independent RDS instance
Any typo in instance class (e.g., db.t3.micr) will cause incorrect configuration
IAM warnings (like SCP deny) can appear but may not affect task completion
🎯 Outcome
Snapshot nautilus-snapshot created successfully ✅
New instance nautilus-snapshot-restore restored successfully ✅
Instance is in Available state with correct configuration ✅
