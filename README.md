# Ventura-OpencoreLegacyPatcher-HD4600

## 黑苹果，戴尔7557，Ventura驱动HD4600
1、下载OpenCore-Patcher-GUI.app  
   https://github.com/dortania/OpenCore-Legacy-Patcher/releases  
2、下载AMFIExemption.kext 并添加到config.plist中的Kernel  ##已添加到EFI\OC\Kexts  
3、打开config.plist → NVRAM → 7C436110-AB2A-4BBB-A880-FE41995C9F82  在boot-args中添加amfi_get_out_of_my_way=1  
   将csr-active-config 置为FF0F0000  
4、将config.plist中Misc → Security找到SecureBootModel置为Disabled  
5、将config.plist中 DP 添加 PciRoot(0x0)/Pci(0x2,0x0) ，仅保留AAPL,ig-platform-id和device-id两项，并将内容修改为自己电脑核显相对应值  
  
   DP中无 PciRoot(0x0)/Pci(0x2,0x0) 会导致 OpenCore-Patcher-GUI.app → post install root patch → start root patching识别不到显卡而灰色无法破解  
     
   DP中PciRoot(0x0)/Pci(0x2,0x0)内容详实会导致黑苹果无法识别显卡而导致无法进入界面  
     
   因此内容越少越好，只需要让黑苹果能够进入界面且OpenCore-Patcher-GUI.app识别到显卡信息即可  
     
6、重启黑苹果，进入恢复模式，点击实用工具，打开终端，输入csrutil disable，确认回车，显示Successfully disabled System Integrity Protection.……即可重启电脑  
7、重启后打开 OpenCore-Patcher-GUI.app 点击 post install root patch 即可发现识别的显卡，点击start root patching完成破解  
8、破解完成后即可自定义修改PciRoot(0x0)/Pci(0x2,0x0)  
  
  
  
## Hackintosh, Dell 7557, Ventura drive HD4600  


1. Download OpenCore-Patcher-GUI.app  
   https://github.com/dortania/OpenCore-Legacy-Patcher/releases  
2. Download AMFIExemption.kext and add it to the Kernel in config.plist ##Already added to EFI\OC\Kexts  
3. Open config.plist → NVRAM → 7C436110-AB2A-4BBB-A880-FE41995C9F82 Add amfi_get_out_of_my_way=1 to boot-args  
   Set csr-active-config to FF0F0000  
4. Open config.plist → Misc → Security found the SecureBootModel and set it to Disabled  
5. Add PciRoot(0x0)/Pci(0x2,0x0) to DP in config.plist, keep only AAPL, ig-platform-id and device-id, and modify the content to the corresponding value of your computer’s nuclear display  
   
    No PciRoot(0x0)/Pci(0x2,0x0) in DP will cause OpenCore-Patcher-GUI.app → post install root patch， can not recognize the graphics card and start root patching button is grayed out， can not be patched  
      
    The detailed content of PciRoot(0x0)/Pci(0x2,0x0) in DP will cause the Hackintosh to fail to recognize the graphics card and make it impossible to enter the interface  
      
    Therefore, the less content the better, just let the Hackintosh can enter the interface and OpenCore-Patcher-GUI.app can recognize the graphics card information
      
6. Restart the black apple, enter the recovery mode, click on the utility, open the terminal, enter csrutil disable, confirm and press Enter, it will display Successfully disabled System Integrity Protection.... to restart the computer  
7. After restarting, open OpenCore-Patcher-GUI.app and click post install root patch to find the recognized graphics card, click start root patching to complete the cracking  
8. After the cracking is completed, you can customize and modify PciRoot(0x0)/Pci(0x2,0x0)  
