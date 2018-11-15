using System;
using System.Collections.Generic;
using System.Linq;

namespace RadixSortWithList
{
	class Program
	{
		static void RadixSortList(List<int> vec)
		{
			int biggest = vec.First();

			List<int> final = new List<int>(vec.Count);

			final.AddRange(new int[vec.Count]);

			int exp = 1;

			foreach (var item in vec)
			{
				if (item > biggest)
				{
					biggest = item;
				}
			}

			while (biggest / exp > 0)
			{
				List<int> bucket = new List<int>();

				bucket.AddRange(new int[vec.Count]);

				for (int i = 0; i < vec.Count; i++)
				{
					bucket[(vec[i] / exp) % 10]++;
				}

				for (int i = 1; i < vec.Count; i++)
				{
					bucket[i] += bucket[i - 1];
				}

				for (int i = vec.Count - 1; i >= 0; i--)
				{
					final[--bucket[(vec[i] / exp) % 10]] = vec[i];
				}

				for (int i = 0; i < vec.Count; i++)
				{
					vec[i] = final[i];
				}

				exp *= 10;
			}

			foreach (var item in final)
			{
				Console.Write(item + " - ");
			}
		}

		static List<int> GenerateRadomVector()
		{
			Random rand = new Random();

			List<int> vector = new List<int>();

			for (int i = 0; i < 10; i++)
			{
				vector.Add(rand.Next(50));
			}

			return vector;
		}

		static void Main(string[] args)
		{
			List<int> randomized = GenerateRadomVector();

			foreach (var item in randomized)
			{
				Console.Write(item + " - ");
			}

			Console.WriteLine("\n Sorted ");

			RadixSortList(randomized);

			while (true)
			{

			}
		}
	}
}
