@patch("builtins.input")
    def test_2(self, input_mock):
        keyword = "computer"
        advanced_option = 2
        output = get_print(input_mock, [keyword, advanced_option, 5])
        expected = print_basic() + keyword + "\n" + print_advanced() + str(advanced_option) + "\n" + print_advanced_option(advanced_option)+ str(5)+"\n"+ "\nHere are your articles: ['Ken Kennedy (computer scientist)', 'Human computer', 'Single-board computer', 'Covariance and contravariance (computer science)', 'Personal computer']\n"
        self.assertEqual(output, expected)

    @patch("builtins.input")
    def test_3(self, input_mock):
        keyword = "computer"
        advanced_option = 3
        output = get_print(input_mock, [keyword, advanced_option, 5])
        expected = print_basic() + keyword + "\n" + print_advanced() + str(advanced_option) + "\n" + print_advanced_option(advanced_option)+ str(5)+"\n"+"\nHere are your articles: Scores (computer virus)\n"
        self.assertEqual(output,expected)

    @patch("builtins.input")
    def test_4(self, input_mock):
        self.maxDiff = None
        keyword = "computer"
        advanced_option = 4
        output = get_print(input_mock,[keyword, advanced_option, "Scores (Computer Virus)"])
        expected = print_basic() + keyword + "\n" + print_advanced() + str(advanced_option) + "\n" + print_advanced_option(advanced_option)+ "Scores (Computer Virus)"+"\n"+"\nHere are your articles: ['Ken Kennedy (computer scientist)', 'Human computer', 'Single-board computer', 'Covariance and contravariance (computer science)', 'Personal computer', 'Scores (computer virus)', 'Solver (computer science)', 'Spawning (computer gaming)', 'List of computer role-playing games', 'Mode (computer interface)']\n" + "Your favorite article is in the returned articles!\n"
        self.assertEqual(output, expected)


    @patch("builtins.input")
    def test_5(self, input_mock):
        self.maxDiff = None
        keyword = "computer"
        advanced_option = 5
        output = get_print(input_mock,[keyword, advanced_option, "dog"])
        expected = print_basic() + keyword + "\n" + print_advanced() + str(advanced_option) + "\n" + print_advanced_option(advanced_option)+ "dog"+"\n"+"\nHere are your articles: ['Ken Kennedy (computer scientist)', 'Human computer', 'Single-board computer', 'Covariance and contravariance (computer science)', 'Personal computer', 'Scores (computer virus)', 'Solver (computer science)', 'Spawning (computer gaming)', 'List of computer role-playing games', 'Mode (computer interface)', 'Edogawa, Tokyo', 'Kevin Cadogan', 'Endogenous cannabinoid', 'Black dog (ghost)', '2007 Bulldogs RLFC season', 'Mexican dog-faced bat', 'Dalmatian (dog)', 'Guide dog', '2009 Louisiana Tech Bulldogs football team', 'Georgia Bulldogs football', 'Endoglin', 'Sun dog', 'The Mandogs', 'Georgia Bulldogs football under Robert Winston', 'Landseer (dog)']\n"
        self.assertEqual(output, expected)
