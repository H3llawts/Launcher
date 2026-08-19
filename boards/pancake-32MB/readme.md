flashing setup

Windows Powershell 

esptool --chip esp32c5 -p COMx -b 460800 --before default_reset --after hard_reset write_flash `
  --flash_mode dio `
  --flash_size 32MB `
  --flash_freq 80m `
  0x2000 bootloader.bin `
  0x8000 partitions.bin `
  0x10000 firmware.bin

Linux/macos

esptool --chip esp32c5 -p /dev/ttyACM0 -b 460800 \
  --before default-reset --after hard-reset \
  write_flash --flash_mode dio --flash_size 32MB --flash_freq 80m \
  0x2000 bootloader.bin \
  0x8000 partitions.bin \
  0x10000 firmware.bin