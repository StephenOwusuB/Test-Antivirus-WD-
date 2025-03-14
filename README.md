# How to Test Antivirus Using EICAR File

1. Go to [EICAR.org](https://www.eicar.org/) to download the EICAR malware test file.
   ![EICAR](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2034.png)
2. SmartScreen will attempt to stop you; select **More detail** and click on **Continue** to see the EICAR malware string.
   ![smartscreen block](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2035.png)
3. Copy the string and paste it into Notepad.
    ![EICAR Script](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2036.png)
4. Save the file. Immediately, you will receive a prompt from Windows Security saying it found a threat and blocked it.
    ![Window Secuirty block](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2037.png)
6. When you go to the location where the test file was stored, you will not see it anymore.  
7. When you open Notepad and try to open the test file from there, it will inform you that the file has been removed.
   ![Window Secuirty block](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2040.png)
9. Go to the Defender portal.
   - Under **Alert**, you will see an alert in the portal saying EICAR_Test_File malware was prevented.
   - Next, select the **Incidents** tab. If you don't see the EICAR test incident, click on **Reset filter**. You should see the incident now.
      ![Incidents & alerts](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2041.png)
   - Click on the EICAR incident. You will receive a pop-up showing the attack map.
      ![Attack Map](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2043.png)
   - Click on the **Alerts** tab at the top. You will see the process tree. Under detection technology, you will see **Client, Heuristic**.
   - Detection status: **Prevented**.
   - Detection source: **Antivirus** (handled by the real-time protection feature of Windows Defender).
   - When you scroll down, you will see the evidence, which includes the entity name, remediation status, and verdict.
   - Under **Alert description**, you will find details on what really happened.
      ![Attack Map](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2044.png)
      ![Attack Description](https://github.com/StephenOwusuB/Implementing-Microsoft-Defender-for-Enterprise-Security/blob/main/images/AV/MDE%20onboard%2045.png)

## Linux

1. Run this command in the terminal to confirm whether real-time protection is turned on:
    ```bash
    mdatp health --field real_time_protection_enabled
    ```
   If you run this command, you should get `1` as the output, which signifies it is enabled.

2. To create the EICAR file, type in:
    ```bash
    curl -o ~/tmp/eicar.com.txt https://secure.eicar.org/eicar.com.txt
    ```

## macOS

1. To create the EICAR file, type in:
    ```bash
    curl -o ~/Downloads/eicar.com.txt https://secure.eicar.org/eicar.com.txt
    ```

---

This should provide clear instructions for testing antivirus using the EICAR file across different platforms. If you need further adjustments or additional information, let me know! 😊
