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
CODI PER CALCULAR LA LLETRA D'UN DNI
using System;

class Program
{
    static void Main()
    {
        string dni;

        do
        {
            Console.WriteLine("Introdueix el número de DNI (8 números, sense lletra): ");
            dni = Console.ReadLine();

            if (dni.Length != 8)
            {
                Console.WriteLine("el DNI ha de tenir obligatoriament 8 números.");
            }
            else if (!EsNumeric(dni))
            {
                Console.WriteLine("Nomes es permeten numeros");
            }

        } while (dni.Length != 8 || !EsNumeric(dni));

        int numero = int.Parse(dni);

        string lletres = "TRWAGMYFPDXBNJZSQVHLCKE";
        int residu = numero % 23;
        char lletra = lletres[residu];

        Console.WriteLine("La lletra del DNI és: " + lletra);
    }

    static bool EsNumeric(string text)
    {
        for (int i = 0; i < text.Length; i++)
        {
            if (!char.IsDigit(text[i]))
                return false;
        }
        return true;
    }
}