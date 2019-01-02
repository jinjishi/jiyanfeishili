# jiyanfeishili
package intership2.dao;
import java.lang.Exception;
import java.util.ArrayList;
import java.util.Scanner;
public class Landing {
	public static void main(String[] args) throws Exception {
		Scanner in=new Scanner(System.in);
		boolean land=false;
		int a,b;
		System.out.println("欢迎来到京东购物");
		UserDaoImpl impl=new UserDaoImpl();
		do {
			System.out.println("请选择登录方式，密码登录选1，QQ登录选2，微信登录选3");
			a=in.nextInt();
			if(a==1)
			{
				System.out.println("请输入用户ID与密码");
				boolean c=true;
				String str1;
				@SuppressWarnings("unused")
		    	ArrayList<User> list=new ArrayList<User>();
				do
				{
					c=true;
					System.out.println("用户ID：");
		    		str1=in.next();
		    		list=impl.getUser2("use shopping select * from [User] where Userid" + "='"+str1+"'");
			    	if(!impl.result)
			    	{
			    		System.out.println("该用户不存在");
			    		c=false;
				    }
				}while(!c);
				System.out.println("密码：");
				String str2=in.next();
			    list=impl.getUser2("use shopping select * from [User] where Userid" + "='"+str1+"' and Password='"+str2+"'");
				if(impl.result)
				{
					System.out.println("登陆成功！");
					land=true;
				}
				else
				{	
					System.out.println("密码不正确，是否重新登录？是填1，否填2");
					b=in.nextInt();
					if(b==2)
					{
						land=true;
					}		
				}
			}
			
			if(a==2)
			{
				System.out.println("请输入QQID与密码");
				boolean c=true;
				String str1;
				@SuppressWarnings("unused")
		    	ArrayList<User> list=new ArrayList<User>();
				do
				{
					c=true;
					System.out.println("QQID：");
		    		str1=in.next();
		    		list=impl.getUser2("use shopping select * from [User] where QQid" + "='"+str1+"'");
			    	if(!impl.result)
			    	{
			    		System.out.println("该用户不存在");
			    		c=false;
				    }
				}while(!c);
				System.out.println("密码：");
				String str2=in.next();
			    list=impl.getUser2("use shopping select * from [User] where QQid" + "='"+str1+"' and QQpassword='"+str2+"'");
				if(impl.result)
				{
					System.out.println("登陆成功！");
					land=true;
				}
				else
				{	
					System.out.println("密码不正确，是否重新登录？是填1，否填2");
					b=in.nextInt();
					if(b==2)
					{
						land=true;
					}		
				}
			}
			
			if(a==3)
			{
				System.out.println("请输入微信ID与密码");
				boolean c=true;
				String str1;
				@SuppressWarnings("unused")
		    	ArrayList<User> list=new ArrayList<User>();
				do
				{
					c=true;
					System.out.println("用户ID：");
		    		str1=in.next();
		    		list=impl.getUser2("use shopping select * from [User] where Wechatid" + "='"+str1+"'");
			    	if(!impl.result)
			    	{
			    		System.out.println("该用户不存在");
			    		c=false;
				    }
				}while(!c);
				System.out.println("密码：");
				String str2=in.next();
			    list=impl.getUser2("use shopping select * from [User] where Wechatid" + "='"+str1+"' and Wechatpassword='"+str2+"'");
				if(impl.result)
				{
					System.out.println("登陆成功！");
					land=true;
				}
				else
				{	
					System.out.println("密码不正确，是否重新登录？是填1，否填2");
					b=in.nextInt();
					if(b==2)
					{
						land=true;
					}		
				}
			}
		}while(land==false);
        in.close();
	}
}
