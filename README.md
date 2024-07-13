import java.util.*;
import java.sql.*;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.*;
import java.lang.reflect.InvocationTargetException;

class Game {
    private static Player currentUser1 = null;
    private static Player currentUser2 = null;
    private static int[] user1map = new int[21];
    private static int[] user2map = new int[21];
    private static Player currentPlayer;
    private static Player opponent;
    private static List<Player> playersList = new ArrayList<>();
    public static ArrayList<Clan> clansList = new ArrayList<>();

    public Game(Player currentPlayer1){
        Scanner scanner = new Scanner(System.in);
        System.out.println("Choose mode to play");
        System.out.println("1. Play two-player game");
        System.out.println("2. Play two-player bet game");
        System.out.println("3. clan war");
        System.out.println("4. play with computer");
        String command = scanner.nextLine();
        switch (command) {
            case "1":
                currentUser1 = currentPlayer1;
                play2playergame(currentPlayer1);
                break;
            case "2":
                System.out.println("How much do you want to play on?");
                int amounttobet = scanner.nextInt();
                currentUser1 = currentPlayer1;
                play2playerbetgame(currentPlayer1 , amounttobet);
            case "3":
                SQL.clanMenu(currentPlayer1);
            case "4":
                currentUser1 = currentPlayer1;
                //playAgainstAIBot(currentPlayer1);
                break;
            default:
                System.out.println("Invalid command");
        }
    }

    private void play2playerbetgame(Player currentPlayer1, int amounttobet) {
    }

    private void play2playergame(Player currentPlayer1) {
    }

}
