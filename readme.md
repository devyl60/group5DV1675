# DV1675XR group 5s Setup Guide
Built with Unreal Engine 5.7

## Prerequisites
Before you begin, ensure you have the following installed:
- Unreal Engine 5.7 or later
- Git
- Git LFS
- Docker Desktop
- VR Headset Drivers?

## Initial Setup
Follow these steps to get the project running on your machine:
# 1. Clone the repository
git clone https://github.com/devyl60/group5DV1675.git
# 2. enter the folder
cd group5DV1675
# 3. Pull large assets with Git LFS
git lfs pull
# 4. Open the project in Unreal Engine
Double klick the .uproject file
If prompted to rebuild modules, say yes

## Development Workflow
# Start from the latest dev branch
git checkout dev
git pull origin dev
# Create a feature branch
git checkout -b feature/your-feature-name
# Make your changes, then commit
git add .
git commit -m "Describe your changes clearly"
# Push your feature branch
git push -u origin feature/your-feature-name

## Manual Container Build
1. Navigate to your project file folder
2. Run the container build
```bash
docker run --rm -ti -v "$(pwd):/project" ghcr.io/epicgames/unreal-engine:dev-5.7 \
  /home/ue4/UnrealEngine/Engine/Build/BatchFiles/RunUAT.sh \
  BuildCookRun -project=/project/DV1675XR.uproject \
  -platform=Linux -build -cook -stage -pak -archive \
  -archivedirectory=/project/Build
