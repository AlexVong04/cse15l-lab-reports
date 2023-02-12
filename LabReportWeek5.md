# Lab Report 3 - Researching Commands
## Grep Options <br>
* **grep -c** <br>
  *Source: https://en.wikibooks.org/wiki/Grep* <br>
  Example 1:
  
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -c "place" travel_guides/berlitz1/WhatTo*.txt
  travel_guides/berlitz1/WhatToDublin.txt:6
  travel_guides/berlitz1/WhatToEdinburgh.txt:3
  travel_guides/berlitz1/WhatToEgypt.txt:4
  travel_guides/berlitz1/WhatToFWI.txt:1
  travel_guides/berlitz1/WhatToFrance.txt:0
  travel_guides/berlitz1/WhatToGreek.txt:1
  travel_guides/berlitz1/WhatToHawaii.txt:0
  travel_guides/berlitz1/WhatToHongKong.txt:10
  travel_guides/berlitz1/WhatToIbiza.txt:9
  travel_guides/berlitz1/WhatToIndia.txt:3
  travel_guides/berlitz1/WhatToIsrael.txt:8
  travel_guides/berlitz1/WhatToIstanbul.txt:8
  travel_guides/berlitz1/WhatToItaly.txt:4
  travel_guides/berlitz1/WhatToJamaica.txt:30
  travel_guides/berlitz1/WhatToJapan.txt:4
  travel_guides/berlitz1/WhatToLakeDistrict.txt:8
  travel_guides/berlitz1/WhatToLasVegas.txt:10
  travel_guides/berlitz1/WhatToLosAngeles.txt:6
  travel_guides/berlitz1/WhatToMadeira.txt:10
  travel_guides/berlitz1/WhatToMalaysia.txt:3
  travel_guides/berlitz1/WhatToMallorca.txt:2
  ```
  The -c in grep outputs the count of matching lines. So in this command I am looking for the number of lines that has the word "place" in each 
  file in berlitz1 that starts with WhatTo. This is useful because you can see which file has the most or least occurence of a certain word.
  
  Example 2:
  
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -c "beautiful" travel_guides/berlitz2/N*.txt
  travel_guides/berlitz2/Nepal-History.txt:0
  travel_guides/berlitz2/Nepal-WhatToDo.txt:0
  travel_guides/berlitz2/Nepal-WhereToGo.txt:4
  travel_guides/berlitz2/NewOrleans-History.txt:0
  ```
  This command is looking for the number of lines that contains the word "beautiful" in each file in berlitz2 that starts with the letter 'N'.
  This could be useful because if you are looking for a certain phrase or topic you can use this command to see which file talks about that 
  phrase or topic the most.
  
* **grep -l** <br>
  *Source: https://en.wikibooks.org/wiki/Grep* <br>
  Example 1: <br>
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -l "ocean" travel_guides/berlitz1/*.txt
  travel_guides/berlitz1/HandRHawaii.txt
  travel_guides/berlitz1/HandRJamaica.txt
  travel_guides/berlitz1/HistoryHawaii.txt
  travel_guides/berlitz1/HistoryMadeira.txt
  travel_guides/berlitz1/IntroMadeira.txt
  travel_guides/berlitz1/WhatToFWI.txt
  travel_guides/berlitz1/WhatToJamaica.txt
  travel_guides/berlitz1/WhatToLosAngeles.txt
  travel_guides/berlitz1/WhereToFWI.txt
  travel_guides/berlitz1/WhereToIbiza.txt
  travel_guides/berlitz1/WhereToItaly.txt
  travel_guides/berlitz1/WhereToJapan.txt
  travel_guides/berlitz1/WhereToLosAngeles.txt
  travel_guides/berlitz1/WhereToMadeira.txt
  ```
  The -l in grep is outputs the files that contain that matching word. In this case, the grep command is looking through each .txt file in berlitz1
  that contains the word ocean. This could be useful because if you had a huge travel_guide catalog like this, you could use this command to see
  which places have a ocean to visit
  
  Example 2:
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -l "noodles" travel_guides/berlitz2/*.txt
  travel_guides/berlitz2/China-WhereToGo.txt
  ```
  In this example, the command is looking through each .txt file in berlitz2 and printing the files that contain the word noodles. This shows another
  example of the -l being useful by seeing which files mention which topic or word.
  
* **grep -n** <br>
  *Source: https://en.wikibooks.org/wiki/Grep* <br>
  Example 1: <br>
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -n "noodles" travel_guides/berlitz2/*.txt
  travel_guides/berlitz2/China-WhereToGo.txt:413:Urumqi is the most modern and most Chinese city on the Si
  lk Road. Downtown avenues are tree-lined, there are dozens of mosques, and the street markets provide sp
  lashes of color. At the largest covered market, the Erdaoqiao Bazaar, vendors sell handmade goods from b
  oots to carpets and herds of sheep and donkey carts ply the alleyways. The most irresistible items are e
  dible: kebabs, homemade noodles, and round flatbreads, cooked on the spot over coal fires.
  ```
  The -n in grep prints out the line number for each matching line. So in this example, the command looks through all the .txt files in berlitz2 and 
  prints the lines that contain the word "noodles along with the line number in that file. This could be useful because you could then use that line
  number to look at the lines around that specific line number to get context or more information.
  
  Example 2:
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -n "paella" travel_guides/berlitz2/Costa-WhatToDo.txt
  7:Most visitors to the Costa del Sol do not plan daytime activities more energetic than lazing on the be
  ach, and save their energy for nightlife. However, sports facilities are in abundance for those who want
   to work off the effects of too much paella during the daylight hours.
  ```
  This command is looking for the line number and matching line that has the word "paella" in the file named Costa-WhatToDo.txt. You can use this 
  information to look up the section in the file containing that line number to get more information about that certain word.
  
* **grep -L** <br>
  *Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html* <br>
  Example 1: <br>
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -L "beach" travel_guides/berlitz1/WhereTo*.txt
  travel_guides/berlitz1/WhereToJerusalem.txt
  travel_guides/berlitz1/WhereToMadrid.txt
  ```
  The -L in grep prints the files that do not contain the matching word. In this example, the command looks through each file starting with
  WhereTo and prints the files that do not contain the word "beach". This could be useful because sometimes you may want to look for files not talking 
  about a certain word. For example, if you have a huge travel catalog like this one and do not like beachs, you can use this command to see which places
  do not have beaches.
  
  Example 2:
  ```
  alexvong@Alexs-MacBook-Pro-5 written_2 % grep -L "busy" travel_guides/berlitz1/WhereTo*.txt
  travel_guides/berlitz1/WhereToEgypt.txt
  travel_guides/berlitz1/WhereToFWI.txt
  travel_guides/berlitz1/WhereToHawaii.txt
  travel_guides/berlitz1/WhereToIbiza.txt
  travel_guides/berlitz1/WhereToMadeira.txt
  ```
  This command looks through each file starting with WhereTo in berlitz1 and prints the files that do not contain the word "busy". This command can 
  narrow down what you are looking for by only showing the files that do not contain a certain word. For example, someone who wants to vacation at 
  somewhere rural and calm may use this command since it eliminates the files that contain the word "busy.

  
