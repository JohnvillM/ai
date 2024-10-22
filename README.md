# ai


int player1Choice;
        try {
            player1Choice = Integer.parseInt(jTextField3.getText());
            if (player1Choice < 1 || player1Choice > 3) {
                jLabel6.setText("Invalid input! Use 1, 2, or 3.");
                jLabel12.setText("CPU Choice: ");
                return;
            }
        } catch (NumberFormatException e) {
            jLabel6.setText("Please enter a valid number (1, 2, or 3).");
            jLabel12.setText("CPU Choice: ");
            return;
        }

        int player2Choice = random.nextInt(3) + 1; // CPU chooses randomly between 1 and 3

        jLabel12.setText("CPU Choice: " + player2Choice);

        String result;

        if (player1Choice == player2Choice) {
            result = "It's a Tie!";
        } else if ((player1Choice == 1 && player2Choice == 3) || 
                   (player1Choice == 2 && player2Choice == 1) || 
                   (player1Choice == 3 && player2Choice == 2)) {
            result = "Player 1 Wins!";
        } else {
            result = "CPU Wins!";
        }
        jLabel6.setText("Result: " + result);
