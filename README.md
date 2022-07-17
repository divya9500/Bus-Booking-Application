# Bus-Booking-Application

package Application;

import java.sql.*;
import java.util.ArrayList;

public class BusApp {

    static int seatRow=5,seatCol=4,sleepRow=7,sleepcol=3,seatcount=4;

    static String busname[]={"Ac Seater : ","Non Ac Seater : ","Ac Seater 2 : ","Non Ac Seater 2 : ","Ac Sleeper : ","Non Ac Sleeper : ","Ac Sleeper 2 : ","Non Ac Sleeper 2 : "};

    static String a1[][] = {{" ", "1", "2", "3"}, {"A", "a", "a", "a"}, {"B", "a", "a", "a"}, {"C", "a", "a", "a"}, {"D", "a", "a", "a"},};
    static String a2[][] = {{" ", "1", "2", "3"}, {"A", "a", "a", "a"}, {"B", "a", "a", "a"}, {"C", "a", "a", "a"}, {"D", "a", "a", "a"},};
    static String a3[][] = {{" ", "1", "2", "3"}, {"A", "a", "a", "a"}, {"B", "a", "a", "a"}, {"C", "a", "a", "a"}, {"D", "a", "a", "a"},};
    static String a4[][] = {{"4 ", "1", "2", "3"}, {"A", "a", "a", "a"}, {"B", "a", "a", "a"}, {"C", "a", "a", "a"}, {"D", "a", "a", "a"},};

    static String a5[][] = {{" ", "1", "2"}, {"A", "a", "a"}, {"B", "a", "a"}, {"C", "a", "a"}, {"D", "a", "a"}, {"E", "a", "a"}, {"F", "a", "a"},};
    static String a6[][] = {{" ", "1", "2"}, {"A", "a", "a"}, {"B", "a", "a"}, {"C", "a", "a"}, {"D", "a", "a"}, {"E", "a", "a"}, {"F", "a", "a"},};
    static String a7[][] = {{" ", "1", "2"}, {"A", "a", "a"}, {"B", "a", "a"}, {"C", "a", "a"}, {"D", "a", "a"}, {"E", "a", "a"}, {"F", "a", "a"},};
    static String a8[][] = {{" ", "1", "2"}, {"A", "a", "a"}, {"B", "a", "a"}, {"C", "a", "a"}, {"D", "a", "a"}, {"E", "a", "a"}, {"F", "a", "a"},};

    static String tableName[] = {"bus1", "bus2", "bus3", "bus4","bus5", "bus6", "bus7", "bus8"};
    static String tableName1[] = {"cancel1", "cancel2", "cancel3", "cancel4","cancel5", "cancel6", "cancel7", "cancel8"};

    static ArrayList<String> snum = new ArrayList<String>();
    static String arr[][] = new String[seatRow][seatCol];
    static String arr1[][] = new String[sleepRow][sleepcol];

    static   String bus1[][]=new String[seatRow][seatCol];
    static String bus2[][]=new String[sleepRow][sleepcol];


    static String aa[][][]={a1,a2,a3,a4,a5,a6,a7,a8};
    static  int c1=0,c2=0,c3=0,c4=0,c5=0,c6=0,c7=0,c8=0;
    static int count[]={c1,c2,c3,c4,c5,c6,c7,c8};



    static int y = 0, c = 0, fees, f;

    static int amount[]={550,450,550,450,700,600,700,600};
    static int canamt[]={275,112,275,112,350,150,350,150};

    public static String [][]seater(int x) {
        for(int i=0;i<seatcount;i++){
            if((x-1)==i )
                arr = aa[i];
        }
        return arr ;
    }

    public static String [][] sleeper(int x){
        for(int i=(seatcount);i<aa.length;i++){
            if((x-1)==(i) )
                arr1 = aa[i];
        }
        return arr1;
    }

    public static void fare(int ch) {
      for(int i=0;i<amount.length;i++){
          if((ch-1)==i){
              fees=canamt[i];
              f=amount[i];
          }}
    }

    public static void fare() {
        for(int i=0;i< busname.length;i++)
            System.out.println(busname[i]+"Rs. "+amount[i]+ " / seat");
    }

    public static void busName() {
        for (int i = 0; i < busname.length; i++)
            System.out.println((i + 1) + " for " + busname[i]);
    }
    //seat number equivalent row and column value
        public static String seatNumber(int n, String s) {
            String seat = "";
            if (n <= seatcount) {
                switch (s) {
                    case "A1":  seat = "11"; break;
                    case "A2":  seat = "12";break;
                    case "A3": seat = "13";break;
                    case "B1": seat = "21";break;
                    case "B2": seat = "22";break;
                    case "B3": seat = "23";break;
                    case "C1": seat = "31";break;
                    case "C2": seat = "32";break;
                    case "C3": seat = "33";break;
                    case "D1": seat = "41";break;
                    case "D2": seat = "42";break;
                    case "D3": seat = "43";break;
                    default:
                        System.out.println("Invalid seat");
                }}
            if (n >seatcount) {
                switch (s) {
                    case "A1": seat = "11";break;
                    case "A2": seat = "12";break;
                    case "B1": seat = "21";break;
                    case "B2": seat = "22";break;
                    case "C1": seat = "31";break;
                    case "C2": seat = "32";break;
                    case "D1": seat = "41";break;
                    case "D2": seat = "42";break;
                    case "E1": seat = "51";break;
                    case "E2": seat = "52";break;
                    case "F1": seat = "61";break;
                    case "F2": seat = "62";break;
                    default:
                        System.out.println("Invalid seat");
                }}
            return seat;
        }
//seat filled details
    public static void details(int ch) {
        int ch1=0;
        if (ch <= seatcount){
            bus1 = seater(ch);
            ch1=1;
        }
        if (ch>seatcount) {
            bus2 = sleeper(ch);
            ch1=2;
        }
        switch (ch1) {
            case 1:
                System.out.println("Upper Deck");
                for (int i = 0; i <seatRow; i++) {
                    for (int j = 0; j < seatCol; j++)
                        System.out.print(bus1[i][j] +"  ");
                    System.out.println("\n----------------");
                    int mid=(seatRow-1)/2;
                    if (i == mid)
                        System.out.println("Lower Deck");
                }
                for(int i=0;i<seatcount;i++){
                    if((ch-1)==i)
                        aa[i]=bus1;
                }
                break;
            case 2:
                System.out.println("Upper Deck");
                for (int i = 0; i < sleepRow; i++) {
                    for (int j = 0; j < sleepcol; j++)
                        System.out.print(bus2[i][j] + "  ");
                    System.out.println("\n----------");
                    int mid=(sleepRow-1)/2;
                    if (i == mid)
                        System.out.println("Lower Deck");
                }
                for(int i=seatcount;i<aa.length;i++){
                    if((ch-1)==(i))
                        aa[i]=bus2;
                }
                break;
        }
    }
//available seat count
 public static void available() {
     c1=0;c2=0;c3=0;c4=0;c5=0;c6=0;c7=0;c8=0;
     for (int k = 0; k < seatcount; k++) {
         bus1 = seater(k + 1);
         count[k] = 0;int c1 = count[k];
         for (int i = 0; i < seatRow; i++) {
             for (int j = 0; j < seatCol; j++) {
                 if (bus1[i][j].equals("a")) {
                     c1++;
                 }
                 count[k] = c1;
             }
         }
     }

     for (int k = seatcount; k < count.length; k++) {
         bus2 = sleeper(k+1);
         count[k] = 0;
         int c2 = count[k];
         for (int i = 0; i < sleepRow; i++) {
             for (int j = 0; j < sleepcol; j++) {
                 if (bus2[i][j].equals("a"))
                     c2++;
                 count[k] = c2;
             }}}
 }
    public static void filterting(){
        available();
        String sc[]={"Ac Seater:","Non Ac Seater:","Ac Sleeper:","Non Ac Sleeper:"};
        int arrcount[]={count[0],count[1],count[4],count[5]};
        int max=0;String max1="";
        for (int i = 0; i <arrcount.length; i++) {
            for (int j = i + 1; j < arrcount.length; j++) {
                if (arrcount[i] == arrcount[j]) {

                if (sc[i].equals("Ac Seater:") && sc[j].equals("Ac Sleeper:") || (sc[i].equals("Non Ac Seater:") && sc[j].equals("Non Ac Sleeper:")) ||
                (sc[i].equals("Non Ac Seater:") && sc[j].equals("Ac Seater:")) || (sc[i].equals("Non Ac Sleeper:") && sc[j].equals("Ac Sleeper:")) ||
                (sc[i].equals("Non Ac Seater:") && sc[j].equals("Ac Sleeper:")) || (sc[i].equals("Non Ac Sleeper:") && sc[j].equals("Ac Seater:"))) {
                        max1 = sc[i];
                        sc[i] = sc[j];
                        sc[j] = max1;
                    }
                } else if (arrcount[i] < arrcount[j]) {
                    max1 = sc[i];sc[i] = sc[j];max = arrcount[i];
                    arrcount[i] = arrcount[j];arrcount[j] = max;sc[j] = max1;
                }
            }
            System.out.println(sc[i] + arrcount[i]);
        }
        System.out.println("------------------------");
    }
\\filterting 
    public static void filterting1(){
        available();
        String sc[]={"Ac Seater 2:","Non Ac Seater 2:","Ac Sleeper 2:","Non Ac Sleeper 2:"};
        int arrcount[]={count[2],count[3],count[6],count[7]};

        int max=0;String max1="";
        for (int i = 0; i <arrcount.length; i++) {
            for (int j = i + 1; j < arrcount.length; j++) {
                if (arrcount[i] == arrcount[j]) {

                    if (sc[i].equals("Ac Seater 2:") && sc[j].equals("Ac Sleeper 2:") || (sc[i].equals("Non Ac Seater 2:") && sc[j].equals("Non Ac Sleeper 2:")) ||
                          sc[i].equals("Non Ac Seater 2:") && sc[j].equals("Ac Seater 2:")) || (sc[i].equals("Non Ac Sleeper 2:") &sc[j].equals("Ac Sleeper 2:")) ||
                         (sc[i].equals("Non Ac Seater 2:") && sc[j].equals("Ac Sleeper 2:")) || (sc[i].equals("Non Ac Sleeper 2:") && sc[j].equals("Ac Seater 2:")))                    {
                        max1 = sc[i];
                        sc[i] = sc[j];
                        sc[j] = max1;
                    }

                } else if (arrcount[i] < arrcount[j]) {
                    max1 = sc[i];sc[i] = sc[j];max = arrcount[i];
                    arrcount[i] = arrcount[j];arrcount[j] = max;sc[j] = max1;
                }
            }
            System.out.println(sc[i] + arrcount[i]);
        }
        System.out.println("------------------------");
    }
}



package Application;
import java.sql.*;
import static Application.mainMethod.dd;

public class App1 extends BusApp {
    static Statement stmt;
    static Connection con;
    static {
        try {
            con = DriverManager.getConnection("jdbc:mysql://localhost:3306/bus", "root", "zoho");
            stmt = con.createStatement();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
    //task 2-Sign Up
    public static void signUp(String id, String password, int age, String gender) throws Exception {
        try {
            String update = "insert into signup values('" + id + "','" + password + "','" + age + "','" + gender + "')";
            stmt.executeUpdate(update);
            System.out.println("Account created..");
            System.out.println("enter 2 for Sign In\n3 for exit");
        } catch (SQLIntegrityConstraintViolationException e) {
            System.out.println("User Id already exists");
            System.out.println("Sign Up failed");
            System.out.println("Again Sign Up for 1 \nexit for 3");
        }

    }
    //admin sign up
    public static void signUp(String id, String password) throws Exception {
        try {
            String update = "insert into signup1 values('" + id + "','" + password + "')";
            stmt.executeUpdate(update);
            System.out.println("Account created..");
            System.out.println("enter 2 for Sign In\n3 for exit");
        } catch (SQLIntegrityConstraintViolationException e) {
            System.out.println("User Id already exists");
            System.out.println("Sign Up failed");
            System.out.println("Again Sign Up for 1 \nexit for 3");
        }

    }
    //task 3-sign in
    public static int signIn(String Userid, String pw) throws Exception {
        int choice = 0;
        String aa[]={"signup","signup1"};

        String retrieve = "select * from "+aa[dd]+" where userid='" + Userid + "' AND password ='" + pw + "'";
        ResultSet rs = stmt.executeQuery(retrieve);

        if (rs.next()) {
            System.out.println("Sign In successful");
            choice = 0;
        } else {
            System.out.println("oops!,enter correct user id and password:");
            System.out.println("Sign In failed");
            System.out.println("Again Sign In for 2 \nexit for 3");
            choice = 1;
        }
        return choice;
    }

    static int colunmNum = 4;

    public static void columnName() {
        System.out.printf("%10s", "UserId");
        System.out.printf("%10s", "SeatNo");
        System.out.printf("%10s", "Name");
        System.out.printf("%10s", "Gender\n");
    }
//ticket cancel details
    public static void cancel(String userid, int bn) throws SQLException {
        String qu = "";
        for (int i = 0; i < tableName.length; i++) {
            if (i == (bn - 1)) {
                String table = tableName[i];
                qu = "select * from " + table + " where userId='" + userid + "'";
                ResultSet rs = stmt.executeQuery(qu);
                System.out.println("Your Seats Are: ");
                columnName();
                c = 0;
                while (rs.next()) {
                    for (int j = 1; j <= 4; j++)
                        System.out.printf("%10s", rs.getString(j));
                    System.out.println("");c++;y=1;
                }
                System.out.println();
            }}
    }


    public static void completecancel(String userid, int bn) throws SQLException {
        for (int i = 0; i < tableName.length; i++) {
            if ((bn-1) == (i)) {
                String query1 = "SELECT * FROM " + tableName[i] + " WHERE userId='" + userid + "' ";
                ResultSet rss = stmt.executeQuery(query1);
                while (rss.next()) {
                    String sn = rss.getString("seat");

                    String s1 = seatNumber(bn, sn);
                    int r1 = Integer.parseInt(String.valueOf(s1.charAt(0)));
                    int c1 = Integer.parseInt(String.valueOf(s1.charAt(1)));
                    aa[i][r1][c1] = "a";
                }
                String query = "INSERT INTO " + tableName1[i] + " SELECT * FROM " + tableName[i] + " WHERE userId='" + userid + "' ";
                stmt.executeUpdate(query);

                stmt.executeUpdate("delete from " + tableName[i] + " where userid='" + userid + "'");
            }
        }
        fare(bn);
        int balamount=(c*fees);
        System.out.println("Return Amount:"+balamount);
        System.out.println("successfully cancelled...");

    }

    public static void partiallycancel(String userid,int bn,int x) throws SQLException {
        for(int j=0;j< tableName.length;j++){
            if((bn-1)==j) {
                for (int i = 0; i < snum.size(); i++) {
                    String sn = snum.get(i);
                    String s1= seatNumber(bn, sn);
                    int r1 = Integer.parseInt(String.valueOf(s1.charAt(0)));
                    int c1 = Integer.parseInt(String.valueOf(s1.charAt(1)));

                    aa[j][r1][c1]="a";
                    String query = "INSERT INTO "+tableName1[i]+" SELECT * FROM "+tableName[i]+" WHERE userId='" + userid + "' AND seat='" + sn + "' ";
                    stmt.executeUpdate(query);
                    stmt.executeUpdate("delete from "+tableName[i]+" where userid='" + userid + "' AND seat='" + sn + "' ");
                }
                fare(bn);
                int balamount=(x*fees);
                System.out.println("Return Amount:"+balamount);
                System.out.println("successfully cancelled...");
            }}

    }

public static void bussummary(int l) throws SQLException {
        String  query = ""; ResultSet rs = null;
        for(int i=0;i<tableName.length;i++){
            int d=0,d1=0;
            if ((l-1) == (i )) {
                System.out.println("BUS NAME : " + busname[i]);
                System.out.println("FILLED SEATS DETAILS : ");
                String query1="select * from "+tableName[i];
                rs= stmt.executeQuery(query1);
                while (rs.next()) {
                    for (int j = 1; j <= colunmNum; j++)
                        System.out.printf("%10s", rs.getString(j));
                    System.out.println("");d++;
                }
                System.out.println();

                System.out.println("CANCELED SEATS DETAILS : ");
                query = "select * from " + tableName1[i];
                ResultSet rs1 = stmt.executeQuery(query);
                columnName();

                while (rs1.next()) {
                    for (int j = 1; j <= colunmNum; j++)
                        System.out.printf("%10s", rs1.getString(j));
                    System.out.println("");d1++;
                }

                fare(l);
                System.out.println("Total Fare Collected:" + ((d * f) + (d1 * fees)) + "(" + d + " tickets " + d1 + " cancellation)");
                System.out.println("-----------------");
            }}}
}


//main method
package Application;
import java.util.Scanner;
import static Application.App1.*;

public class mainMethod extends BusApp {
static int dd=0,ch=0;
public static void main(String[] args) throws Exception {

        int p1 = 0, q = 0, temp = 0;
        String gend = "", id1 = "", name = "", s = "";
        Scanner sc=new Scanner(System.in);

        System.out.println("Sign Up or Sign In to manage your trips");
        System.out.println("1 for sign up\n2 for sign In\n3 for Bus Summary\n4 for exit");
        int choice = 1;

        while (choice != 0) {
            choice = sc.nextInt();

            switch (choice) {
                case 1://sign up
                    System.out.println("Enter the user id:");
                    String id = sc.next();

                    System.out.println("Enter the password :");
                    String password = sc.next();

                    System.out.println("Enter Your Age :");
                    int age = sc.nextInt();

                    System.out.println("Enter your Gender :");
                    String gender = sc.next();

                    signUp(id, password, age, gender);
                    break;
                case 2://signIn
                    dd=0;
                    System.out.println("Enter the user id:");
                    id1 = sc.next();
                    System.out.println("Enter the password :");
                    String password1 = sc.next();
                    choice = signIn(id1, password1);
                    System.out.println("-----------------------");
                    break;

                case 3:

                    while (choice!=0) { dd=1;
                        System.out.println("1 for sign up\n2 for sign In\n3 for exit");
                        choice = sc.nextInt();
                        System.out.println("Enter the user id:");
                        id1 = sc.next();
                        System.out.println("Enter the password :");
                        String pw = sc.next();
                        if (choice == 1)
                            signUp(id1, pw);
                        if (choice == 2)
                           choice= signIn(id1, pw);
                    }
                    if(choice==0) {
                        int l = 1;
                        while (l != 0) {
                       busName();
                            l = sc.nextInt();
                            if(l==0)
                                System.exit(0);
                            bussummary(l);
                        }}
                    break;
                case 4:
                    System.exit(0);
            }
        }
        int choice1 = 0;
        while (choice1 != 4) {
            System.out.println("1 for booking \n2 for Cancellation \n3 for Filtering \n4 for exit");
            choice1 = sc.nextInt();

            if (choice1 == 1){
                choice = 0;temp=0;}

            if (choice1 == 2) {
                System.out.println("Enter your UserId:");
                String uid = sc.next();
                System.out.println("Enter your Bus number:");
                int bn = sc.nextInt();
                cancel(uid, bn);
                choice = 1;
                if (y == 1) {
                    System.out.println("Enter 1 for completely cancel (all seats) \nEnter 2 for partially cancel (selectedseats)");
                    int oc = sc.nextInt();
                    if (oc == 1) {
                        completecancel(uid, bn);
                        y = 0;
                    }
                    if (oc == 2) {

                        System.out.println("enter the no.of cancel tickets:");
                        int x = sc.nextInt();

                        for (int i = 0; i < x; i++) {
                            System.out.println("Enter the seat number"+(i+1)+" :");
                            String sn = sc.next();
                            snum.add(sn);
                        }
                        partiallycancel(uid, bn, x);
                        y = 0;
                    }
                } else
                    System.out.println("Not found");
            }
            if (choice1 == 3) {

                filterting();
                filterting1();
                System.out.println("Enter 1 for Ac bus \nEnter 2 for Non Ac bus\n" + "Enter 3 for both");
                int op = sc.nextInt();
                if (op == 1) {
                    System.out.println("Enter 1 for Ac Seater\nEnter 2 for Ac Seater 2\n"+"Enter 3 for Ac Sleeper \nEnter 4 for Ac Sleeper 2");
                    ch = sc.nextInt();
                    if (ch == 2)
                        ch = 3;
                    if (ch ==3 )
                        ch = 5;
                    if(ch==4)
                        ch=7;
                    temp = 1;
                    choice = 0;
                }
                if (op == 2) {
                 System.out.println("Enter 1 for Non Ac Seater\nEnter 2 for Non Ac Seater 2\n"+"Enter 3 for Non Ac Sleeper \nEnter 4 for Non Ac Sleeper 2");
                    ch = sc.nextInt();
                    if (ch == 1)
                        ch = 2;
                    if (ch == 2)
                        ch = 4;
                    if (ch == 3)
                        ch = 6;
                    if (ch == 4)
                        ch = 8;
                    temp = 1;
                    choice = 0;
                }
                if (op == 3)
                    temp = 0;
            }
            if (choice1 == 4)
                System.exit(0);


         if (choice == 0) {
                if (temp == 0) {
                    available();
                   for(int i=0;i<busname.length;i++) {
                       System.out.println(busname[i] + count[i]);
                   }
                    System.out.println("-----------------");
                    fare();
                    System.out.println("------------------");
                  busName();
                    ch = sc.nextInt();
                }
                details(ch);
                System.out.println("how many tickets you can book");
                int ticket = sc.nextInt();
                int seat = 0, amount1 = 0, tol;

                for(int h=0;h<count.length;h++){
                    if((ch-1)==h){
                        seat=count[h];
                        amount1=amount[h];
                    }
                }

                String seatNumber[] = new String[ticket];
                int row[] = new int[ticket];
                int col[] = new int[ticket];
                String gender[] = new String[ticket];
                int d = 0, rerun = 0;
                if (seat >= ticket) {

                    for (int m = 0; m < ticket; m++) {
                        System.out.println("Enter your name"+(m+1)+" :");
                        name = sc.next();
                        System.out.println("Enter your gender"+(m+1)+" :(ex:m or f)");
                        gend = sc.next();

                        rerun = 0;
                        while (rerun != 1) {

                            System.out.println("Enter the Seat number"+(m+1)+":");
                            s = sc.next();

                            String snum = seatNumber(ch, s);
                            p1 = Integer.parseInt(String.valueOf(snum.charAt(0)));
                            q = Integer.parseInt(String.valueOf(snum.charAt(1)));
                            //seat selection
                            if (ch <= seatcount) {
                                if (ticket == 1) {
                                    if (bus1[p1][q].equals("a")) {

                                        String l1 = bus1[p1][1];
                                        String l2 = bus1[p1][2];
                                        String l3 = bus1[p1][3];

                                        if (((l1.equals("a") && l2.equals("a") && l3.equals("a"))) || (l1.equals("f") && l2.equals("a") && gend.equals("f"))
                                                || (gend.equals("f") && l1.equals("a") && l2.equals("f") && (l3.equals("a") || l3.equals("f")))
                                                || (l1.equals("m") && l2.equals("a") && gend.equals("m")) || (gend.equals("m") && l1.equals("a") && l2.equals("m")
                                                && (l3.equals("a") || l3.equals("m")))) {
                                            bus1[p1][q] = gend;
                                            d = 1;
                                        } else
                                            System.out.println("this seat not available");

                                       details(ch);
                                    } else
                                        System.out.println("this seat is already fill...");

                                }
                                if (ticket > 1) {
                                    if (bus1[p1][q].equals("a")) {
                                        bus1[p1][q] = gend;
                                        d = 1;
                                    } else {
                                        System.out.println("this seat is already fill...");
                                    }

                                   details(ch);
                                }
                            }

                            if (ch > seatcount) {
                                if (ticket == 1) {
                                    if (bus2[p1][q].equals("a")) {
                                        String l1 = bus2[p1][1];
                                        String l2 = bus2[p1][2];

                                        if (((l1.equals("a") && l2.equals("a"))) || (l1.equals("f") && gend.equals("f")) || (gend.equals("f") && l2.equals("f")) || (l1.equals("m") && gend.equals("m")) || (l2.equals("m") && gend.equals("m"))) {
                                            bus2[p1][q] = gend;
                                            d = 1;
                                        } else {
                                            System.out.println("this seat not available");
                                        }
                                        details(ch);

                                    }else
                                        System.out.println("this seat is already fill...");
                                }

                                if (ticket > 1) {
                                    if (bus2[p1][q].equals("a")) {
                                        bus2[p1][q] = gend;
                                        d = 1;
                                    } else
                                        System.out.println("this seat is already fill...");

                                 details(ch);
                                }
                            }
                            rerun = d;
                        }
                        row[m] = p1;
                        col[m] = q;
                        gender[m] = gend;
                        seatNumber[m] = s;

                        for(int i=0;i<tableName.length;i++){
                            if((ch-1)==i)
                                stmt.executeUpdate("insert into "+tableName[i]+" values('" + id1 + "','" + s + "','" + name + "','" + gend + "')");
                        }
                    }

                    if (d == 1) {
                        tol = ticket * amount1;
                        System.out.println("total fare is :" + tol);
                        System.out.println("confirmation of the booking...\n1 for yes\n2 for no");
                        int op = sc.nextInt();
                        switch (op) {
                            case 1://confirmation
                                System.out.println("enter the amount:");
                                int amunt = sc.nextInt();
                                if (tol == amunt) {
                                    System.out.println("successfully Booked");
                                }
                                break;
                            case 2:// not confirmation
                                if (ch <= seatcount)
                                    bus1 = seater(ch);
                                if (ch > seatcount)
                                    bus2 = sleeper(ch);

                                for(int i=0;i< aa.length;i++){
                                    if((ch-1)==i && ch<=seatcount)
                                        aa[i]=bus1;
                                    if((ch-1)==i && ch>seatcount)
                                        aa[i]=bus2;
                                }

                                for (int m = 0; m < row.length; m++) {

                                    p1 = row[m];
                                    q = col[m];
                                    gend = gender[m];

                                    if (ch <= seatcount) {
                                        if (bus1[p1][q].equals(gend))
                                            bus1[p1][q] = "a";
                                    }

                                    if (ch > seatcount) {
                                        if (bus2[p1][q].equals(gend))
                                            bus2[p1][q] = "a";
                                    }

                                    stmt.executeUpdate("SET SQL_SAFE_UPDATES = 0");
                                    for(int i=0;i<tableName.length;i++){
                                        if((ch-1)==i)
                                            stmt.executeUpdate("delete from "+tableName[i]+" where userid='" + id1 + "' AND seat='" + seatNumber[m] + "' AND   gender='" + gend + "'");
                                    }
                                }
                                break;
                        }
                    }
                } else
                    System.out.println("This bus available seats " + seat);
            }
        }}}
        
