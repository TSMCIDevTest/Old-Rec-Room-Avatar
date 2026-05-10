```
#############################################################
#############################################################
#############################################################
########                                             ########
#######                                               #######
######   ###########################################   ######
######   ###########################################   ######
######   ###########################################   ######
######                                                 ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ############   #############   ############   ######
######   ###########################################   ######
######   ###########################################   ######
######     #######################################     ######
######        #################################        ######
######   ##       #########################       ##   ######
######   ######         #############         ######   ######
######   ##########                       ##########   ######
######   ###########################################   ######
######   ###########################################   ######
######   ###########################################   ######
######   ###########################################   ######
######   ###########################################   ######
#######                                               #######
########                                             ########
#############################################################
#############################################################
#############################################################

            +-----------------------------------+
            |  THANK YOU FOR PLAYING REC ROOM!  |
            +-----------------------------------+

From the whole Rec Room team, thank you for playing our game!

                 Be excellent to each other!
```

## File Types

*.binpb           Binary Protocol Buffer data
*.glb             glTF Binary 3D model (importable into Blender, Unity, etc.)
*.jpg / *.png     Image files

## File Structure

Not all files and folders will be present in every
export. Contents depend on your export settings and
the content of your room.

```
{AvatarData}/
|
|- README.txt                                  # This file
|- ExportLog_*.log                             # Export process log
|- Warnings.log                                # Export warnings (if any)
|- descriptor_set.binpb                        # Protobuf descriptor set
|- AvatarData.binpb                            # Avatar data in binpb format
|
|- Avatar_2D/                                  # 2D Avatar Captures
| +- Capture360_*.png                          # 360 degree image capture
| +- Pose_*.png                                # Posed image capture
|
|- Avatar_3D/                                  # 3D Avatar Captures
| +- AvatarData_Me.glb                         # Avatar mesh
```

### descriptor_set.binpb

You can read this file as proto descriptors with
'protoc' or 'buf'.

With protoc (https://protobuf.dev/installation/):

```sh
protoc --decode=google.protobuf.FileDescriptorSet \
  google/protobuf/descriptor.proto \
  < descriptor_set.binpb
```

With buf (https://github.com/bufbuild/buf):

```sh
buf convert \
  --type google.protobuf.FileDescriptorSet \
  --from descriptor_set.binpb \
  --to -#format=txtpb
```

Note that these are only descriptions of the .proto
files. They are not the original .proto files used
in game.
";
