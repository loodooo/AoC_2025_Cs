# AoC_2025_Cs
these are my solutions for advent of code 2025 writen in c# (for college reasons)
### --- Day 1: Secret Entrance ---
```c#
        public static void Day1()
        {
            int Part1 = 0, Part2 = 0, Angle = 50, Temp, Dirrection, Value;

            foreach (String x in fUtils.GetInput("day1.txt"))
            {
                Value = int.Parse(x.Substring(1));

                if (x[0] == 'R') { Dirrection = 1; } else { Dirrection = -1; }

                Temp = Angle + Value * Dirrection;
                if (Angle != 0 && Temp <= 0) { Part2 += Math.Abs(Temp) / 100 + 1; }
                else { Part2 += Math.Abs(Temp) / 100; }
                Temp = ((Temp % 100) + 100) % 100;

                if (Temp == 0) Part1++;

                Angle = Temp;
            }
            Console.WriteLine($"Part1: {Part1}\nPart2: {Part2}");
        }
```
