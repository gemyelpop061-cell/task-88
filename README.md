using System;
using System.Linq;

class Program
{
    static void Main()
    {
        try
        {
            Console.Write("أدخل نصاً للتحقق من حروف العلة: ");
            string userInput = Console.ReadLine();

            CheckForVowels(userInput);
            
            Console.WriteLine("النص صحيح ويحتوي على حروف علة.");
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
            throw new Exception("النص المدخل فارغ!");
        }

        char[] vowels = { 'a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U' };
        bool hasVowels = text.Any(c => vowels.Contains(c));

        if (!hasVowels)
        {
            throw new Exception("النص لا يحتوي على أي حروف علة!");
        }
    }
}


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        try
        {
            List<int> numbers = new List<int>();
            Console.WriteLine("أدخل أرقاماً صحيحة (اكتب 'done' للإنتهاء):");

            while (true)
            {
                string input = Console.ReadLine();
                if (input.ToLower() == "done")
                    break;

                if (int.TryParse(input, out int num))
                {
                    if (numbers.Contains(num))
                    {
                        throw new Exception($"الرقم {num} مكرر!");
                    }
                    numbers.Add(num);
                }
                else
                {
                    Console.WriteLine("يرجى إدخال رقم صحيح صالح.");
                }
            }

            Console.WriteLine("تم إدخال جميع الأرقام بنجاح بدون تكرار.");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"[Exception]: {ex.Message}");
        }
    }
}
