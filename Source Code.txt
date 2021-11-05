/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package array1d.java;

import java.util.Scanner;

/**
 *
 * @author alfir
 */
public class Array1DJava {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner a = new Scanner(System.in);
        String makanan[];
        
        makanan = new String[8];
        int index=0, //index array
            harga[] = new int[8],
            harga2[] = new int[8],    
            pilih = 0,
            total = 0,
            totalasli = 0,    
            bayar,
            ulang,
            pesan,    
            pelanggan,
            diskon = 0,
            grandtotal = 0;
        
        System.out.print("Klik 1 untuk mendapatkan diskon : ");    
        pelanggan = a.nextInt();
        
        System.out.println("-----------------Daftar Menu-------------------");
        
        do {
            System.out.println("1.Sate Ayam  (2.000 / tusuk)");
            System.out.println("2.Sate Kambing  (3500 / tusuk)");
            System.out.println(" ");
            System.out.println("3.Soto  (10.000)");
            System.out.println("4.Rawon (20.000)");
            System.out.println("5.Pecel (8000)");
            System.out.println(" ");
            System.out.println("6.Bakso (10.000(porsi sederhana))");
            System.out.println("7.Bakso (15.000(porsi spesial))");
            System.out.println("8.Bakso (35.000(porsi spesial + sumsum))");
            System.out.println("Selesai Klik (9)");
            
            System.out.println("---------------------------------");
            
            System.out.print("Pilih : ");
            pilih=a.nextInt();
            System.out.print("Jumlah Pesan : ");
            pesan = a.nextInt();
            System.out.println(pesan);
            
                
            System.out.println("------------------------");
            
            switch(pilih){
                    case 1: 
                        makanan[index] = "Sate Ayam";
                        harga[index] = 2000;
                        pesan = pesan;
                        harga2[index] = harga[index] * pesan * 95/100;
                        diskon = diskon + 5;
                        if(pilih == 1){
                            total = pesan * harga[index] * 95/100;
                        } else if (pelanggan == 2){
                            total = pesan * harga[index];
                        }
                    break;
                    case 2: 
                        makanan[index] = "Sate Kambing";
                        harga[index] = 3500;
                        harga2[index] = harga[index] * pesan * 95/100;
                        diskon = diskon + 5;
                        if(pilih == 1){
                            total = pesan * harga[index] * 95/100;
                        } else if (pelanggan == 2){
                            total = pesan * harga[index];
                        }
                    break;
                     case 3: 
                         makanan[index] = "Soto";
                         harga[index] = 10000;
                         harga2[index] = harga[index] * pesan;
                         total = total + 10000;
                    break;
                     case 4: 
                         makanan[index] = "Rawon";
                         harga[index] = 20000;
                         harga2[index] = harga[index] * pesan; 
                         total = total + 20000;
                         diskon = diskon + 5;
                    break;
                     case 5: 
                         makanan[index] = "Pecel";
                         harga[index] = 8000;
                         harga2[index] = harga[index] * pesan; 
                         total = total + 8000;
                         diskon = diskon + 5;
                    break;
                     case 6: 
                         makanan[index] = "Bakso Sederhana";
                         harga[index] = 10000;
                         harga2[index] = harga[index] * pesan;
                         total = total = 10000;
                    break;
                    case 7: 
                        makanan[index] = "Bakso Spesial";
                        harga[index] = 15000;
                        harga2[index] = harga[index] * pesan;
                        total = total + 15000;
                    break;
                    case 8: 
                        makanan[index] = "Bakso Spesial + Sumsum";
                        harga[index] = 35000;
                        harga2[index] = harga[index] * pesan * 95/100;
                        diskon = diskon + 5;
                        if(pilih == 1){
                            total = pesan * harga[index] * 95/100;
                        } else if (pelanggan == 2){
                            total = pesan * harga[index];
                        }
                    break;
            }
            index++;
            
            if(index > 9) {
                System.out.println("Kapasitas Sudah Penuh :");
            } 
            
        } while(pilih != 9); 
        
        totalasli = total;
    
        
        //menampilkan makanan yang di beli
        System.out.println("--------------Daftar Struk-------------");
        for(int i = 0; i < index-1; i++){
            System.out.println((i+1)+ "."+makanan[i]+ "\t Rp."+harga[i] + "x" +pesan);
        }
       
        System.out.println("------------------------");
               
         for(int i = 0; i < index-1; i++){
            System.out.println((i+1)+ "."+makanan[i]+"\t Rp."+harga2[i]);
        }
         System.out.println("Diskon 5% Untuk Sate/Bakso Sumsum");
         System.out.println("Grand Total                            : " + totalasli);
         System.out.print("Pembayaran                               : ");
         bayar=a.nextInt();
          int kembalian = bayar - total;
           
         for(int q = 0; q < totalasli; q++){
                if(totalasli == 0){
                System.out.println("Anda Lunas");
            } else if(bayar < totalasli) {
                System.out.print("Masukkan Nominal Uang             : ");
                bayar = a.nextInt();
                
            }    
        }
            if(bayar >= totalasli){
                kembalian = bayar - totalasli ;
                System.out.println("Kembalian Anda                  : Rp." + kembalian);
                System.out.println("Maaf pak outputnya kurang indah :)");
            }
            
           
             
            
    }
    
}
