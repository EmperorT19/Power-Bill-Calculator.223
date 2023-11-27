# Power-Bill-Calculator.223
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace powerbillcalculator
{
    class Program
    {
        static void Main(string[] args)
        {
            bool isRunning = true;
            while (isRunning)
            {
                try
                {
                    Console.WriteLine("Welcome to the Monthly Power Bill Calculator!");

                    // Input power consumption
                    Console.Write("Please enter the power consumption in kWh: ");
                    double powerConsumption = double.Parse(Console.ReadLine());

                    // Input usage type
                    Console.WriteLine("Please enter the usage type:");
                    Console.WriteLine("1. Residential.");
                    Console.WriteLine("2. Commercial.");
                    Console.WriteLine("3. Industrial.");
                    Console.Write("Select choice: ");
                    int usageType = int.Parse(Console.ReadLine());

                    double tariffRate = 0;

                    // Determine tariff rate based on usage type
                    if (usageType == 1)
                    {
                        tariffRate = 12.50;
                    }
                    else if (usageType == 2)
                    {
                        tariffRate = 15.75;
                    }
                    else if (usageType == 3)
                    {
                        tariffRate = 18.90;
                    }

                    // Calculate total bill and display breakdown
                    double totalBill = powerConsumption * tariffRate;

                    Console.WriteLine($"Breakdown for {usageType} usage:");
                    Console.WriteLine($"Power Consumption: {powerConsumption} kWh");
                    Console.WriteLine($"Tariff Rate: {tariffRate} KES/kWh");
                    Console.WriteLine($"Total Bill: {totalBill} KES");
                    Console.Write("Press enter to exit.");
                }
                catch
                {
                    Console.WriteLine("Wrong input. Try again");
                    continue;
                }
                Console.ReadKey();
                isRunning = false;
            }
        }

    }
}
