# xlnx-5.4-ac-3165

This is a three-party driver

Apply to xlnx kernel under driver/net/wireless/intel

Remember to apply the firmware to the "/lib/firmware/"

This driver had successfully compiled under ZYNQMP

```
dmesg | grep iw
[    8.084812] iwlwifi 0000:01:00.0: enabling device (0000 -> 0002)
[    8.141423] iwlwifi 0000:01:00.0: loaded firmware version 29.1044073957.0 op_mode iwlmvm
[    8.200546] iwlwifi 0000:01:00.0: Detected Intel(R) Dual Band Wireless AC 3165, REV=0x210
[    8.247130] iwlwifi 0000:01:00.0: base HW address: 
[    8.307847] ieee80211 phy0: Selected rate control algorithm 'iwl-mvm-rs'
```

```
01:00.0 Network controller: Intel Corporation Wireless 3165 (rev 81)
        Subsystem: Intel Corporation Dual Band Wireless AC 3165
        Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
        Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
        Latency: 0
        Interrupt: pin A routed to IRQ 50
        Region 0: Memory at e0000000 (64-bit, non-prefetchable) [size=8K]
        Capabilities: [c8] Power Management version 3
                Flags: PMEClk- DSI+ D1- D2- AuxCurrent=0mA PME(D0+,D1-,D2-,D3hot+,D3cold+)
                Status: D0 NoSoftRst- PME-Enable- DSel=0 DScale=0 PME-
        Capabilities: [d0] MSI: Enable+ Count=1/1 Maskable- 64bit+
                Address: 00000000fd480000  Data: 0000
        Capabilities: [40] Express (v2) Endpoint, MSI 00
                DevCap: MaxPayload 128 bytes, PhantFunc 0, Latency L0s <512ns, L1 unlimited
                        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
                DevCtl: Report errors: Correctable- Non-Fatal- Fatal- Unsupported-
                        RlxdOrd+ ExtTag- PhantFunc- AuxPwr+ NoSnoop+ FLReset-
                        MaxPayload 128 bytes, MaxReadReq 128 bytes
                DevSta: CorrErr- UncorrErr- FatalErr- UnsuppReq- AuxPwr+ TransPend-
                LnkCap: Port #0, Speed 2.5GT/s, Width x1, ASPM L1, Exit Latency L0s <4us, L1 <32us
                        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
                LnkCtl: ASPM Disabled; RCB 64 bytes Disabled- CommClk-
                        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
                LnkSta: Speed 2.5GT/s, Width x1, TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
                DevCap2: Completion Timeout: Range B, TimeoutDis+, LTR+, OBFF Via WAKE#
                DevCtl2: Completion Timeout: 16ms to 55ms, TimeoutDis-, LTR-, OBFF Disabled
                LnkCtl2: Target Link Speed: 2.5GT/s, EnterCompliance- SpeedDis-
                         Transmit Margin: Normal Operating Range, EnterModifiedCompliance- ComplianceSOS-
                         Compliance De-emphasis: -6dB
                LnkSta2: Current De-emphasis Level: -3.5dB, EqualizationComplete-, EqualizationPhase1-
                         EqualizationPhase2-, EqualizationPhase3-, LinkEqualizationRequest-
        Capabilities: [100 v1] Advanced Error Reporting
                UESta:  DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
                UEMsk:  DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
                UESvrt: DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
                CESta:  RxErr- BadTLP- BadDLLP- Rollover- Timeout- NonFatalErr-
                CEMsk:  RxErr- BadTLP- BadDLLP- Rollover- Timeout- NonFatalErr+
                AERCap: First Error Pointer: 00, GenCap- CGenEn- ChkCap- ChkEn-
        Capabilities: [140 v1] Device Serial Number bc-54-2f-ff-ff-5b-71-6f
        Capabilities: [14c v1] Latency Tolerance Reporting
                Max snoop latency: 0ns
                Max no snoop latency: 0ns
        Capabilities: [154 v1] L1 PM Substates
                L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
                          PortCommonModeRestoreTime=30us PortTPowerOnTime=60us
                L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
                           T_CommonMode=0us LTR1.2_Threshold=0ns
                L1SubCtl2: T_PwrOn=10us
        Kernel driver in use: iwlwifi
        Kernel modules: iwlwifi
```

```

ubuntu@zynqmp:~$ iperf3 -s
-----------------------------------------------------------
Server listening on 5201
-----------------------------------------------------------
Accepted connection from 192.168.1.3, port 52617
[  5] local 192.168.1.50 port 5201 connected to 192.168.1.3 port 52618
[ ID] Interval           Transfer     Bandwidth       Retr  Cwnd
[  5]   0.00-1.00   sec  9.54 MBytes  80.0 Mbits/sec    0    145 KBytes
[  5]   1.00-2.00   sec  14.5 MBytes   122 Mbits/sec    0    539 KBytes
[  5]   2.00-3.00   sec  14.0 MBytes   117 Mbits/sec    0    539 KBytes
[  5]   3.00-4.00   sec  11.9 MBytes  99.7 Mbits/sec    0    539 KBytes
[  5]   4.00-5.00   sec  14.1 MBytes   118 Mbits/sec    0    539 KBytes
[  5]   5.00-6.00   sec  12.7 MBytes   106 Mbits/sec    0    539 KBytes
[  5]   6.00-7.00   sec  12.8 MBytes   107 Mbits/sec    0    539 KBytes
[  5]   7.00-8.00   sec  10.4 MBytes  87.4 Mbits/sec    0    539 KBytes
[  5]   8.00-9.00   sec  11.8 MBytes  98.7 Mbits/sec    0    539 KBytes
[  5]   9.00-10.00  sec  10.7 MBytes  89.9 Mbits/sec    0    539 KBytes
[  5]  10.00-11.00  sec  9.37 MBytes  78.6 Mbits/sec    0    539 KBytes
[  5]  11.00-12.00  sec  9.34 MBytes  78.3 Mbits/sec    0    539 KBytes
[  5]  12.00-13.00  sec  9.29 MBytes  77.9 Mbits/sec    0    539 KBytes
[  5]  13.00-14.00  sec  11.4 MBytes  95.6 Mbits/sec    0    539 KBytes
[  5]  14.00-15.00  sec  10.5 MBytes  87.9 Mbits/sec    0    539 KBytes
[  5]  15.00-16.00  sec  14.0 MBytes   117 Mbits/sec    0    539 KBytes
[  5]  16.00-17.00  sec  13.4 MBytes   113 Mbits/sec    0    539 KBytes
[  5]  17.00-18.00  sec  11.4 MBytes  95.6 Mbits/sec    0    539 KBytes
[  5]  18.00-19.00  sec  14.0 MBytes   117 Mbits/sec    0    539 KBytes
[  5]  19.00-20.00  sec  11.6 MBytes  97.3 Mbits/sec    0    539 KBytes
[  5]  20.00-21.00  sec  10.4 MBytes  87.4 Mbits/sec    0    539 KBytes
[  5]  21.00-22.00  sec  11.7 MBytes  98.0 Mbits/sec    0    539 KBytes
[  5]  22.00-23.00  sec  9.62 MBytes  80.7 Mbits/sec    0    539 KBytes
[  5]  23.00-24.00  sec  9.19 MBytes  77.1 Mbits/sec    0    539 KBytes
[  5]  24.00-25.00  sec  9.25 MBytes  77.6 Mbits/sec    0    539 KBytes
[  5]  25.00-26.00  sec  10.5 MBytes  87.9 Mbits/sec    0    539 KBytes
[  5]  26.00-27.00  sec  5.88 MBytes  49.3 Mbits/sec    0    539 KBytes
[  5]  27.00-28.00  sec  7.17 MBytes  60.1 Mbits/sec    0    539 KBytes
[  5]  28.00-29.00  sec  9.37 MBytes  78.6 Mbits/sec    0    539 KBytes
[  5]  29.00-30.00  sec  8.15 MBytes  68.4 Mbits/sec    0    539 KBytes
[  5]  30.00-30.08  sec  0.00 Bytes  0.00 bits/sec    0    539 KBytes
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bandwidth       Retr
[  5]   0.00-30.08  sec   328 MBytes  91.4 Mbits/sec    0             sender
[  5]   0.00-30.08  sec  0.00 Bytes  0.00 bits/sec                  receiver
```
