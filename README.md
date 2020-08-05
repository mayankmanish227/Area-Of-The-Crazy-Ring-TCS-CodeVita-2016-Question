# Area-Of-The-Crazy-Ring-TCS-CodeVita-2016-Question


import java.util.*;
import java.lang.Math.*;
public class HelloWorld
{

     public static void main(String []args)
     {  
        Scanner sc=new Scanner(System.in);
        double n1=sc.nextDouble();
        double m1=sc.nextDouble();
        double n2=sc.nextDouble();
        double m2=sc.nextDouble();
        double n3=sc.nextDouble();
        double m3=sc.nextDouble();
        
        long start=System.currentTimeMillis();
        
        double a=(double)Math.sqrt((Math.pow((n1-n2),2)+(Math.pow((m1-m2),2))));
        String astr=String.format("%.11f",a);
        a=Double.parseDouble(astr);
        
        double b=(double)Math.sqrt((Math.pow((n2-n3),2)+(Math.pow((m2-m3),2))));
        String bstr=String.format("%.11f",b);
        b=Double.parseDouble(bstr);
        
        double c=(double)Math.sqrt((Math.pow((n3-n1),2)+(Math.pow((m3-m1),2))));
        String cstr=String.format("%.11f",c);
        c=Double.parseDouble(cstr);
        
        if(a+b<c || b+c<a || a+c<b)
        {
            System.out.println("Not Possible");
        }
        else
        {
            double s=(a+b+c)/2;
            if(s==0)
            {
                System.out.println("Not Possible");
            }
            else
           {
                double R=(a*b*c)/Math.sqrt((a+b+c)*(a+b-c)*(a+c-b)*(b+c-a));
                double r=Math.sqrt(((s-a)*(s-b)*(s-c))/s);
                double big=Math.PI*R*R;
                double small=Math.PI*r*r;
                System.out.format("%.2f",big-small);
                System.out.println();
           }
        }
        long end=System.currentTimeMillis();
        System.out.println(end-start+"ms");
     }
}
