package com.samsung.test;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.LineNumberReader;
import java.util.ArrayList;

/**
 * Reader Writer
 * @author xuqiuyu
 * @date 2017年9月16日
 * @version 1.0
 */
public class ReaderAndWriteTest {
	public static void main(String[] args) throws IOException {
		//字符和字流的差别
		//chabie();
		
		//fileWrirer();
		//第一行和最后一行 第二行和倒数第二行交换
		//test();
		
		//LineNumberReader练习
		LineNumberReader lnr = new LineNumberReader(new FileReader("a.txt"));
		String s;
		lnr.setLineNumber(20);
		while((s = lnr.readLine()) != null){
			System.out.println(lnr.getLineNumber()+" "+s);
		}
		/*int b;
		while((b = lnr.read()) != -1){
			System.out.print(lnr.getLineNumber()+" "+(char)b);
		}*/
				
	}

	private static void test() throws FileNotFoundException, IOException {
		BufferedReader br = new BufferedReader(new FileReader("biji.txt"));
		BufferedWriter bw = new BufferedWriter(new FileWriter("biji-copy.txt"));
		ArrayList<String> list = new ArrayList<>();
		String b;
		while((b = br.readLine()) != null){
			list.add(b);
		}
		for(int i = list.size()-1;i>=0;i--){
			bw.write(list.get(i));
			bw.newLine();
			
		}
		br.close();
		bw.close();
	}

	private static void fileWrirer() throws IOException {
		FileWriter fw = new FileWriter("c.txt");
		fw.write("哇哈哈哈就是对方可垃圾上单付款了就是看到了福建省地方！");
		fw.write(44);
		fw.write("\n\r");
		fw.write("结束！");
		fw.close();
	}

	private static void chabie() throws FileNotFoundException, IOException {
		FileReader fr =  new FileReader("b.txt");
		int len;
		while((len = fr.read()) != -1){
			System.out.print((char)len);
		}
		fr.close();
		
		FileInputStream fis = new FileInputStream("b.txt");
		int len1;
		while((len1 = fis.read()) != -1){
			System.out.print((char)len1);
		}
	}
}
