application-to-check-os-version
===============================

c# code to check os version
using System;

namespace determineOS_CS
{  
class Class1
   {
      static void Main(string[] args)
      {
         // Get OperatingSystem information from the system namespace.
         System.OperatingSystem osInfo =System.Environment.OSVersion;
         
         // Determine the platform.
         switch(osInfo.Platform)
         {
            // Platform is Windows 95, Windows 98, 
            // Windows 98 Second Edition, or Windows Me.
            case System.PlatformID.Win32Windows:
         
               switch (osInfo.Version.Minor)
               {
                  case 0:
                     Console.WriteLine ("Windows 95");
                     break;
                  case 10:
                     if(osInfo.Version.Revision.ToString()=="2222A")
                        Console.WriteLine("Windows 98 Second Edition");
                     else
                        Console.WriteLine("Windows 98");
                     break;
                  case  90:
                     Console.WriteLine("Windows Me");
                     break;
               }
               break;
         
            // Platform is Windows NT 3.51, Windows NT 4.0, Windows 2000,
            // or Windows XP.
            case System.PlatformID.Win32NT:

               switch(osInfo.Version.Major)

               {
                  case 3:
                     Console.WriteLine("Windows NT 3.51");
                     break;
                  case 4:
                     Console.WriteLine("Windows NT 4.0");
                     break;
                  case 5:
                     if (osInfo.Version.Minor==0) 
                        Console.WriteLine("Windows 2000");
                     else
                        Console.WriteLine("Windows XP");
                     break;
               }break;
         }
         Console.ReadLine ();
      }
   }
}
					
