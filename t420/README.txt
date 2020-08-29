the pci8086 rom files are the vga bioses for intel hd 3000 & 4000. I somehow acquired 2 different versions of the same version vga bios, which were included named intel_hd*.rom.

the config files are coreboot's configs that go in the root of coreboot folder named as .config

also for each cpu, there's a different setting in coreboot/mainboard/lenovo/t420/Kconfig

for ivybridge set
select NORTHBRIDGE_INTEL_IVYBRIDGE

for sandybridge set
select NORTHBRIDGE_INTEL_SANDYBRIDGE

coreboot_sandybridge_1.rom uses sanybridge cpu with id of 8086, 0116
coreboot_sandybridge_2.rom uses sandybridge cpu with id of 8086, 0126
coreboot_ivybridge.rom uses ivybridge cpu with id of 8086, 0166

for adding links (which doesn't seem to work for primary vgabios so this is irrelevant)
./cbfstool coreboot.rom add -f ../t420/links -n links -t raw

for adding boot menu wait, supposed to be 6.5 seconds, im pretty sure it's faster than that
./cbfstool coreboot.rom add-int -i 6500 -n etc/boot-menu-wait
