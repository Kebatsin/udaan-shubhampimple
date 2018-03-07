# udaan-shubhampimple
the following code can be run with the help of GSON package. The GSON2.2.jar has to be added to the IDE. 
________________________________________________________________________________________________________________________________________
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

package solution1;
package com.javacreed.examples.gson.part1;
/**
 *
 * @author PAT
 */
import java.util.*;
import java.io.*;
import com.google.gson.Gson;
import com.google.gson.GsonBuilder;

class Solution1{

  public static void main(String args[]){
      
       Scanner sc = new Scanner(System.in);
       String sURL = "https://www.oneindia.com/india/from-swiggy-to-go-to-hell-the-tantrums-karti-chidambaram-is-throwing-in-jail-2654060.html";
      
      URL url = new URL(sURL);
      HttpURLConnection request = (HttpURLConnection) url.openConnection();
      request.connect();

      // Convert to a JSON object to print data
      JsonParser jp = new JsonParser(); //from gson
      JsonElement root = jp.parse(new InputStreamReader((InputStream) request.getContent())); //Convert the input stream to a json element
      JsonObject rootobj = root.getAsJsonObject(); //May be an array, may be an object. 
      String[] dataArray = new String[10000];
      dataArray = rootobj.get("articles").getAsArray();
 

       
       String b = "articles.title";

       for(int j = 0; j < dataArray.length; j++){
       
       for(int i = 0; i <= (a.length() - b.length()); i++)
       {
               if(dataArray[j].substring(i,i+b.length()).equalsIgnoreCase(b))
               System.out.println(dataArray[j]);

       }
       }

}
}
