# Step 1: Download MinIO Client
wget https://dl.min.io/client/mc/release/linux-amd64/mc
chmod +x mc
sudo mv mc /usr/local/bin/mc

# Step 2: Rename to avoid conflict with Midnight Commander
sudo mv /usr/local/bin/mc /usr/local/bin/mcli

# Step 3: Configure your S3 alias
mcli alias set mymedia https://s3.malipopopote.solutions 3bY4PKLwGasfHNxZJR5Q DliAj71QHBx9zJSKarmnUPbeR8gdFfXZTkuoVqGC --api s3v4

# Step 4: Navigate to your folder and upload
cd ~/Desktop/Gigs/mcpx
mcli cp --recursive product_images-20260317T100322Z-1-001 mymedia/media/

# Step 5: Verify upload
mcli ls mymedia/media/
