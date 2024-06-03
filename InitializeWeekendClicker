# Set the coordinates to click
$x = 100
$y = 200

# Infinite loop to repeat the click
while ($true) {
    # Move the mouse to the specified coordinates
    Add-Type -TypeDefinition @"
    using System;
    using System.Runtime.InteropServices;
    public class Mouse {
        [DllImport("user32.dll", CharSet = CharSet.Auto, CallingConvention = CallingConvention.StdCall)]
        public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
        private const int MOUSEEVENTF_LEFTDOWN = 0x02;
        private const int MOUSEEVENTF_LEFTUP = 0x04;
        public static void LeftClick(long x, long y) {
            mouse_event(MOUSEEVENTF_LEFTDOWN | MOUSEEVENTF_LEFTUP, x, y, 0, 0);
        }
    }
"@

    # Perform a left click
    [Mouse]::LeftClick($x, $y)

    # Wait for 30 seconds
    Start-Sleep -Seconds 30
}
