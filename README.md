public class Main {
    static boolean gameFinished=false;
    static final char [][] gameGrid = new char[][]{
            {'-','-','-'},
            {'-','-','-'},
            {'-','-','-'}
    };

    public static void main(String[] args) {
        Player playerGame = new Player();
        byte moveOfPlayers=1;
        while (gameFinished==false) {

            playerGame.update(gameGrid);
            moveOfPlayers=playerGame.getMoveCounter();
            if(moveOfPlayers>9) {
                gameFinished=true;
            }//
            for (int i = 0; i < gameGrid.length; i++) {
                for (int j = 0; j < gameGrid[i].length; j++) {


                    if (moveOfPlayers>5) {

                        if ((gameGrid[0][0] == gameGrid[0][1]) && (gameGrid[0][1] == gameGrid[0][2]) && (gameGrid[0][0] != '-')) {
                            gameFinished = true;
                        }
							if ((gameGrid[1][0] == gameGrid[1][1]) && (gameGrid[1][1] == gameGrid[1][2]) && (gameGrid[1][1] != '-')) {
                            gameFinished = true;
                        }
                        if ((gameGrid[2][0] == gameGrid[2][1]) && (gameGrid[2][1] == gameGrid[2][2]) && (gameGrid[2][2] != '-')) {
                            gameFinished = true;
                        }

                        if ((gameGrid[0][0] == gameGrid[1][0]) && (gameGrid[1][0] == gameGrid[2][0]) && (gameGrid[0][0] != '-')) {
                            gameFinished = true;
                        }
                        if ((gameGrid[0][1] == gameGrid[1][1]) && (gameGrid[1][1] == gameGrid[2][1]) && (gameGrid[1][1] != '-')) {
                            gameFinished = true;
                        }
                        if ((gameGrid[0][2] == gameGrid[1][2]) && (gameGrid[1][2] == gameGrid[2][2]) && (gameGrid[2][2] != '-')) {
                            gameFinished = true;
                        }

                        if ((gameGrid[0][0] == gameGrid[1][1]) && (gameGrid[1][1] == gameGrid[2][2]) && (gameGrid[2][2] != '-')) {
                            gameFinished = true;
                        }
                        if ((gameGrid[0][2] == gameGrid[1][1]) && (gameGrid[1][1] == gameGrid[2][0]) && (gameGrid[2][0] != '-')) {
                            gameFinished = true;
                        }
                    }

                    System.out.print(gameGrid[i][j] + "\t");
					}
                System.out.println();
            }
        }

        if (gameFinished==true){
            if (moveOfPlayers<9){
                if (moveOfPlayers%2==0) {
                    System.out.println("zero  winners!");
                } else {
                    System.out.println("crosses winners!");
                }
            } else {
                System.out.println("Equal!");
            }
            System.out.println("Game is over!");
        }
    }
}
