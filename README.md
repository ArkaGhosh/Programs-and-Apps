Programs-and-Apps
=================

class PE1
{
    public static void main(String args[])
    {
        int sum=0;                          // initialzing sum to 0.
        for(int i=1;i<=1000;i++)
        {
            if(i%3==0 || i%5==0)
            {
                sum+=i;                    //updating sum
            }
        }
        System.out.println(sum);
    }
}


class PE2
{
    public static void main(String args[])
    {
        long a=1,b=2,i=0,temp;
        long sum=0;
        while(i<4000000)
        {
            temp=i;                                  // storing last number 
            i=a+b;                                   // calculating the next fibonacci number
            if(i%2==0)
            {
                sum+=i;                              // calculating sum
            }
            a=b;
            b=temp;
        }
        System.out.println(sum);
    }
}


import java.util.*;
class PE3
{
    public static void main(String args[])
    {
        Scanner input=new Scanner(System.in);               //accepting input number
        System.out.println("Enter a number");
        long num=input.nextLong();
        long result=1,inprod=num;                           // initializing result to default values inprod(intermediate product)
        for(long i=2;i<=inprod;i++)
        {
            if(inprod%i==0)                                 // checking if inprod is divisible by 
            {
                inprod/=i;                                  // dividing by i if divisible            
                result=(i>result)?i:result;                 // updating result
                if(inprod==1)
                {
                   break;
                } 
                i=2;                                        // starting again from the first prime
            }
        }
        System.out.println(result);
    }
}


class PE4
{
    public static boolean isPal(int num)
    {
        int rem=0,rev=0,tens=1,n=num,save=num;          // rem(remainder),rev(reverse number)
        for(int i=1;n>0;i++)
        {
            tens*=10;                                    // calculating the number of digits and updating the multiplier
            n/=10;
        }
        n=save;
        while(tens>0)
        {
            rem=n%10;
            n/=10;
            tens/=10;
            rev+=rem*tens;
        }
        return rev==save;
    }
    public static void main(String args[])
    {
        int result=0;
        for(int i=100;i<=999;i++)
        {
            for(int j=i;j<=999;j++)                     
            {
                if(PE4.isPal(i*j))
                {
                    if((i*j)>result)
                    {
                        result=i*j;
                    }
                }
            }
        }
        System.out.println(result);
    }
}


class PE5
{
    public static void main(String args[])
    {
        boolean flag=false;
        long count,i=1000;                      // starting from a large number
        while(!(flag))                          // found the number yet?
        {
            count=0;
            i++;
            for(long j=1;j<=20;j++)
            {
                if((i%j)==0)
                {
                    count++;                  //  by how many numbers is it divisible?
                }
            }
            if(count==20)                   // is it divisible by all 20?
            {
                flag=true;
            }
            else
            {
                flag=false;
            }
        }
        System.out.print(i);
    }
}



class PE6
{
    public static void main(String args[])
    {
        long result=0,sumsusq=0,sumsqsu=0,sum=0;                    // sumsusq(sum of squares); sumsqsu(square of sums)
        for(int i=1;i<=100;i++)
        {
            sumsqsu+=i*i;
            sum+=i;
        }
        sumsusq=sum*sum;
        result=sumsusq-sumsqsu;
        System.out.println(result);
    }
}



class PE7
{
    public static boolean isPrime(long num)             // is it a prime?
    {
        boolean flag=false;
        int count=0;
        for(long i=1;i<=num;i++)
        {
            if(num%i==0)
            {
                count++;
            }
        }
        if(count==2)
        flag=true;
        else 
        flag=false;
        
        return flag;
    }
    public static void main(String args[])
    {
        int count=0;
        for(long l=1;;l++)                          // infinite loop (keeps searching for the number)
        {
            if(PE7.isPrime(l))
            {
                count++;
            }
            if(count==10001)
            {
                System.out.println(l);
                break;
            }
        }
    }
}



import java.util.*;
class PE8
{
    public static void main(String args[])
    {
        Scanner input=new Scanner(System.in);
        System.out.println("Enter the length of the number");               // accepting the length if the number to fix the length of the array
        int length=input.nextInt();
        int array[]=new int[length];
        for(int i=0;i<length;i++)
        {
            System.out.println("Enter the "+(i+1)+"th digit of the number");          
            array[i]=input.nextInt();                                       // storing the number
        }
        int result=0;
        for(int i=0;i<length-4;i++)
        {
            int prod;
            prod=array[i]*array[i+1]*array[i+2]*array[i+3]*array[i+4];
            if(prod>result)
            {
                result=prod;
            }
        }
        System.out.println(result);
    }
}


class PE9
{
    public static boolean isPythagorean(int a,int b,int c)      // is (a,b,c) a pythagorean triplet?
    {
        if(c*c==(a*a+b*b))
        return true;
        else
        return false;
    }
    public static void main(String args[])
    {
        boolean flag=false;
        for(int i=1;i<=1000;i++)
        {
            for(int j=i;j<=1000;j++)
            {
                for(int k=j;k<=1000;k++)
                {
                    if((i+j+k)==1000)
                    {
                        if(PE9.isPythagorean(i,j,k))
                        {
                            flag=true;
                            System.out.println(i+"*"+j+"*"+k+"="+i*j*k);
                            break;
                        }
                    }
                }
                if(flag)
                {
                    break;
                }
            }
            if(flag)
            {
                break;
            }
        }
    }
}



class PE10
{
    public static void main(String args[])
    {
        long sum=0;
        for(long i=1;i<2000000;i++)
        {
            if(PE7.isPrime(i))
            {
                sum+=i;
            }
        }
    }
}



import java.lang.Math;
class PE12
{
    public static int num_div(long n)
    {
        long num=n;
        int count=0;
        for(long i=1;i<=Math.sqrt(num);i++)
        {
            if(num%i==0)
            {
                count++;
            }
        }
        if((Math.pow(Math.sqrt(num),2))==(num^2))
        {
            return count*2-1;
        }
        else
        {
            return count*2;
        }
    }
    public static void main (String args[])
    {
        long num=0;
        for(long i=1;;i++)
        {
            num+=i;
            if(PE12.num_div(num)>500)
            {
                System.out.println(num);
                break;
            }
        }
    }
}


class PE14
{
    public static long length(long n)
    {
        long num=n;
        long count=0;
        while(num!=1)
        {
            if(num%2==0)
            {
                num/=2;
            }
            else
            {
                num=3*num+1;
            }
            count++;
        }
        return count;
    }
    public static void main(String args[])
    {
        long max=0,l,num=0;
        for(long i=1;i<1000000;i++)
        {
            l=PE14.length(i);
            if(l>max)
            {
                max=l;
                num=i;
            }
        }
        System.out.println("Length :"+max+" Number :"+num);
    }
}


