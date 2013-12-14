SI3604
======
package tugasbesar;

import java.io.*;
import java.util.Scanner;

public class FileIndex {

    public static void main(String[] args) {

        DoubleLinkedList ddl = new DoubleLinkedList();
        Scanner input = new Scanner(System.in);

        String path = "E:/20_newsgroups";
        File folder = new File(path);

        String isi[] = folder.list();

        for (int i = 0; i < 1; i++) {

            File folder2 = new File(path + "/" + isi[i]);
            String[] subFolder = folder2.list();

            for (int j = 0; j < subFolder.length; j++) {
                File file = new File(path + "/" + isi[i] + "/" + subFolder[j]);
                String contains = "";
                String tmp;
                try {
                    BufferedReader br = new BufferedReader(new FileReader(file));
                    while ((tmp = br.readLine()) != null) {
                        contains += tmp;
                    }
                } catch (IOException e) {
                }
                
                ddl.IsiNext(subFolder[j], isi[i] + "/" + subFolder[j], contains);
            }
            
            
