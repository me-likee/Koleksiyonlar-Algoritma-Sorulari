# Koleksiyonlar-Algoritma-Sorulari

// Soru - 1: Klavyeden girilen 20 adet pozitif sayının asal ve asal olmayan olarak 2 ayrı listeye atın. (ArrayList sınıfını kullanara yazınız.)

// Negatif ve numeric olmayan girişleri engelleyin.
// Her bir dizinin elemanlarını büyükten küçüğe olacak şekilde ekrana yazdırın.
// Her iki dizinin eleman sayısını ve ortalamasını ekrana yazdırın.
using System.Collections.Generic;
using System.Collections;
namespace arraylist
{
     class program
     {
        public static bool asalmi(int sayi)
        {
            bool durum = false;
 
            for (int i = 2; i < sayi; i++)
            {
                if (sayi % i == 0) 
                {
                    durum = false;
                    break;
                }
                else
                {
                    durum = true;
                }
            }
            if(sayi==2)
            {
                durum=true;
            }
            return durum;
        }
        public static bool kontrol(int sayi)
            {
                bool durum = false;
              
                    if (sayi < 0) 
                    {
                        durum = false;
                       
                    }
                    else
                    {
                        durum = true;
                    }
                return durum;
            }
        static void Main(string[] args)
        {
            ArrayList asal=new ArrayList(); 
            ArrayList asalolmayan=new ArrayList(); 
            int asaltoplam=0;
            int asalolmayantoplam=0;
            int asalort=0;
            int asalolmayanort=0;

            for (int i = 0; i < 20; i++)
            {
                Console.WriteLine("Lütfen  {0}. Sayı Giriniz;",i+1);

                int sayilar=int.Parse(Console.ReadLine());
                if(kontrol(sayilar))
                {
                    if(asalmi(sayilar))
                    {
                        asal.Add(sayilar);
                        asaltoplam+=sayilar;
                    }
                    else
                    {
                        asalolmayan.Add(sayilar);
                        asalolmayantoplam+=sayilar;
                    }
                }
                else
                {
                    Console.WriteLine("Lütfen Pozitif Bir Sayi Giriniz");
                }
          
            }
            asalort=asaltoplam/20;
            asalolmayanort=asalolmayantoplam/20;

            Console.WriteLine("ASAL SAYILAR");
            foreach (int sayi in asal)
                Console.Write(sayi + "    ");

            Console.WriteLine();

            Console.WriteLine("ASAL OLMAYAN SAYILAR");
            foreach (int sayi in asalolmayan)
                Console.Write(sayi + "    ");

            Console.WriteLine("---------------------");

            Console.WriteLine("ASAL SAYILAR ORTALMA:"+asalort);
            Console.WriteLine("ASAL OLMAYAN SAYILAR ORTALMA:"+asalolmayanort);
            Console.WriteLine("ASAL OLMAYAN SAYI ADET:"+asal.Count);
            Console.WriteLine("ASAL  SAYI ADET:"+asalolmayan.Count);

            asalolmayan.Sort();
            asal.Sort();
            Console.WriteLine("-------------ASAL OLMAYAN  SAYI SIRALAMASI------------");
            Console.WriteLine();
            foreach (int sayi in asalolmayan)
                Console.Write(sayi+ "    ");

            Console.WriteLine("-------------ASAL SAYI SIRALAMASI------------");
            Console.WriteLine();
            foreach (int sayi in asal)
                Console.Write(sayi+ "    ");
                
        }
            

    }
}

// Soru - 2: Klavyeden girilen 20 adet sayının en büyük 3 tanesi ve en küçük 3 tanesi bulan, her iki grubun kendi içerisinde ortalamalarını alan ve bu ortalamaları ve ortalama toplamlarını console'a yazdıran programı yazınız. (Array sınıfını kullanarak yazınız.)
namespace soru2
{
    class sorular2
    {
         static void Main(string[] args)
         {
            ArrayList girilensayi=new ArrayList(); 
            ArrayList enbüyüksayilar=new ArrayList(); 
            ArrayList enküçüksayilar=new ArrayList(); 

            for (int i = 0; i < 20; i++)
                {
                    Console.WriteLine("Lütfen  {0}. Sayı Giriniz;",i+1);

                    girilensayi.Add(Console.ReadLine());
            
                }
            girilensayi.Sort();
             foreach (var item in girilensayi)
            {
                Console.WriteLine("-------------:"+item);
            }

             for (int i = 0; i < 3; i++)
             {
                enküçüksayilar.Add(girilensayi.IndexOf(i));
                Console.WriteLine("enküçüksayilar:"+enküçüksayilar);
             }

              for (int i = 17; i < 20; i++)
             {
                enbüyüksayilar.Add(girilensayi.IndexOf(i));
                   Console.WriteLine("enbüyüksayilar"+enbüyüksayilar);
             }
            
           
           
           
         }
    }
}

// Soru - 3: Klavyeden girilen cümle içerisindeki sesli harfleri bir dizi içerisinde saklayan ve dizinin elemanlarını sıralayan programı yazınız.

namespace soru3
{
    class sorular4
    {
         static void Main(string[] args)
         {
            ArrayList sesliharf=new ArrayList();
            string cumle=Console.ReadLine();
            string liste="aeıioöuü";
             for (int i = 0; i < cumle.Length; i++)
             {
                  if (liste.Contains(cumle[i]))
                    {
                        sesliharf.Add(cumle[i]);
                    }
             }
          
            foreach (var item in sesliharf)
            {
                Console.WriteLine(sesliharf);
            }
         }
    }
}
