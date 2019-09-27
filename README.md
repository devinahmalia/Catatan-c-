using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace Latihan_02
{
    abstract class BentukBenda
    {
        protected double luas;
        public abstract double Luas();
    }

    class SegiTiga : BentukBenda
    {
        double alas, tinggi;
        public SegiTiga(double LebarAlas, double Tinggi)
        {
            alas = LebarAlas;
            tinggi = Tinggi;
            luas = Luas();
        }

        public override double Luas()
        {
            luas = alas * tinggi / 2.0;
            return luas;
        }

        public override string ToString()
        {
            string hasil = "Segi Tiga"
            + "\n\tAlas\t:" + alas
            + "\n\tTinggi\t:" + tinggi
            + "\n\tLuas\t:" + luas;
            return hasil;
        }
    }

    class SegiEmpat : BentukBenda
    {
        double sisi;
        public SegiEmpat(double Sisi)
        {
            sisi = Sisi;
            luas = Luas();
        }

        public override double Luas()
        {
            luas = sisi * sisi;
            return luas;
        }

        public override string ToString()
        {
            string hasil = "Segi Empat"
            + "\n\tSisi\t:" + sisi
            + "\n\tLuas\t:" + luas;
            return hasil;
        }
    }

    class Lingkaran : BentukBenda
    {
        double jari;
        public Lingkaran(double Jari)
        {
            jari = Jari;
            luas = Luas();
        }

        public override double Luas()
        {
            luas = 3.14 * jari * jari;
            return luas;
        }

        public override string ToString()
        {
            string hasil = "Lingkaran"
            + "\n\tjari\t:" + jari
            + "\n\tluas\t:" + luas;
            return hasil;
        }
    }


    class Program
    {
        static void Main(string[] args)
        {
            SegiTiga segi3 = new SegiTiga(2.4, 5.0);
            Console.WriteLine(segi3);
            Console.ReadKey();

            SegiEmpat segi4 = new SegiEmpat(3.0);
            Console.WriteLine(segi4);
            Console.ReadKey();

            Lingkaran lingkaran = new Lingkaran(10.0);
            Console.WriteLine(lingkaran);
            Console.ReadKey();
        }
    }
}
