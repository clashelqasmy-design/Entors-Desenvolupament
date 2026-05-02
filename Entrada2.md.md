# Entrada 2: part 3a de l’activitat

En aquesta entrada explico com he fet la part 3a de l’activitat.

Primer he pensat quin tipus de programa podria fer, no molt facil pero tampoc complicat, i aquest es el de la suma dels diferents caracters del DNI.

Aquest és el codi que he fet:

using System;

class Program
{
    static void Main()
    {
        Console.Write("Introdueix el número de DNI (sense lletra): ");
        string dni = Console.ReadLine();

        int suma = 0;

        for (int i = 0; i < dni.Length; i++)
        {
            suma += int.Parse(dni[i].ToString());
        }

        Console.WriteLine("La suma de les xifres és: " + suma);
    }
}