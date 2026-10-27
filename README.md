using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<int> numbers = new List<int>();
        Console.WriteLine("Enter integers (type 'done' to finish):");

        while (true)
        {
            try
            {
                string input = Console.ReadLine();
                if (input.ToLower() == "done")
                    break;

                if (int.TryParse(input, out int num))
                {
                    if (numbers.Contains(num))
                    {
                        throw new Exception($"Number {num} is a duplicate!");
                    }
                    numbers.Add(num);
                }
                else
                {
                    Console.WriteLine("Please enter a valid integer.");
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine($"[Exception]: {ex.Message}");
            }
        }

        Console.WriteLine("All numbers entered successfully without duplicates.");
    }
}



+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

using System;
using System.Linq;

class Program
{
    static void Main()
    {
        try
        {
            Console.Write("Enter a string to check for vowels: ");
            string userInput = Console.ReadLine();

            CheckForVowels(userInput);
            
            Console.WriteLine("The text is valid and contains vowels.");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"[Exception]: {ex.Message}");
        }
    }

    public static void CheckForVowels(string text)
    {
        if (string.IsNullOrEmpty(text))
        {
            throw new Exception("Input text is empty!");
        }

        char[] vowels = { 'a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U' };
        bool hasVowels = text.Any(c => vowels.Contains(c));

        if (!hasVowels)
        {
            throw new Exception("The text does not contain any vowels!");
        }
    }
}
