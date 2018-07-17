#### Continue Learning Notes - 5

######  Continue: Thursday 12th July
+ *How the web works* lesson explains how browsers connect to a server to retrieve web pages. Describes the role of domains, IPs, DNS(Domain Name System) and host servers. What is the headers and body requests and response cycle.

>* to check the IP of a website, open the terminal `ping www.facebook.com` and it will print the IP address. To quite press `ctrl+c`. I can then take that number and drop it in the browser web address and it will take me to facebook.
>* Humans can't remember all the IP addresses out there and that is why the DNS is extremely useful. It searches for the IP address and send it back to us.
>* To check your own IP address type `curl ifconfig.me` in terminal.
>* After testing `curl ifconfig.me` it is very slow and I researched if there is an alternative and `curl v4.ifconfig.co` instantly prints your IP.
>* Now we have the IP address for the website we need to access. Our browser connects to the host server and asks for permission to access content. This is called *Request*.
>* The way our browser asks for content is to provide an *HTTP header* in the request. This header is text content that contains information about our browser among other things.
>>* The HTTP protocol supports different request methods such as GET, PUT, PATCH, POST, and DELETE. In our www.facebook.com case our browser made a GET request meaning we simply want to get back some content and we are not posting or providing any content ourselves.
>>* Servers use status codes defined as a three digit number. This number determines the state of the request and gives insight into the success or failure of your request. The most common code you see when browsing the web is 200 meaning your request was successful.
>>* Request Headers which includes our User-Agent details. This gives the server information about our operating system and our browser.
>* If the server accepts your request it will send back a response. The response comes in the form of another header and a body.
>* Response body shows the HTML content that was sent back to our browser. The response body comes in form of HTML, CSS, or JavaScript code.
>* When this content is received by our browser, it begins to render the webpage content from this code.

Few *__protocols__* to know about:
>* Hypertext transfer protocol => HTTP
>* File transfer protocol => FTP

Two of the most important protocols:
>* Transmission control protocol => TCP
>* Internet protocol => IP

>* Internet service provider => ISP.
>>* The ISP routes the request to a server further up the chain on the Internet. Eventually, the request will hit a domain name server (DNS).
>>* This server will look for a match for the domain name you've typed in. If it finds a match, it will direct your request to the proper server's IP address. If it doesn't find a match, it will send the request further up the chain to a server that has more information.
>>* The request will eventually come to our Web server. Our server will respond by sending the requested file in a series of packets.
>>* Packets are parts of a file that range between 1,000 and 1,500 bytes. Packets have headers and footers that tell computers what's in the packet and how the information fits with other packets to create an entire file.
>>* Each packet travels back up the network and down to your computer.

+ Local VS Remote
>* Local or client-side refers to your computer.
>* Remote or server-side refers to a computer that is somewhere else in the world. In the case of the web this is typically a web server.

+ Front-End VS Back-End
>* Front-end development refers to writing the code that is interpreted by the browser locally (client-side). HTML, CSS, and JavaScript are front-end languages.
>* Back-end development refers to any programming language running on the remote server. Ruby, PHP, Node, Python, Java, ASP.NET, as well as database query languages like SQL are common programming languages that run server-side.

__Summary:__
>* DNS servers associate a domain name with a particular IP address.
>* IP addresses define the unique location of a computer on the internet.
>* The communication between your browser and servers is done through the request and response cycle, which is made up of headers and a response body made up of HTML, CSS, or JavaScript.

+ Also, I worked on *__HTML Fundamentals__* and I create a website along with the instructor. Next lesson contains lots of HTML resources and I want to check them.
>* HTML Language Code Reference, ISO Language codes. Check it on https://www.w3schools.com/tags/ref_language_codes.asp

######  Saturday 14th July
+ Today I worked on *__HTML Album Cover__* and the rest of this section *__Front-End HTML Fundamentals__*. Next section in *__Intro to HTML/CSS__* is *__Front-End HTML5__*.

+ I learned about a new tag `<span></span>` plus previously `<img>`, `<h1></h1>` to `<h6></h6>`, `<p></p>` and `<a></a>`. All of the previous tags have an opening and closing tags except `<img>` is a self closing tag. I also learned about attributes where we can add them in the opening tag to provide more information about the tag.

+ I learned about *Developer tools* where we can change our HTML & CSS code in my browser and test my code and results but once I refresh the page my tests will go back to its original code so I have to change the source code. It is a great way to experiment and learn about different behaviours.

######  Sunday 15th July
+ I finished the first lab in *__More on Hashes__* which consists of 4 methods. It took me a while to solve the first method but I've learned a lot through the process.

```Ruby
# Write your code here.
def dictionary
  dictionary = {
    "hello" => "hi",
    "for" => "4",
    "four" => "4",
    "to" => "2",
    "two" => "2",
    "too" => "2",
    "be" => "b",
    "you" => "u",
    "at" => "@",
    "and" => "&"
  }
end
```

Here is my first method:

```Ruby
def word_substituter(tweet)
  tweet_array = tweet.split(" ")
  tweet_array.each_with_index do |word, index|
    if dictionary.keys.include?(word.downcase)
      tweet_array.delete_at(index) && tweet_array.insert(index, dictionary[word.downcase])
    end
  end
  tweet_array.join(" ")
end
```
In the previous method I had to `split` the string to array of words then iterate over the words and their indices and check if the dictionary hash contain this word it will remove this original word and replace it with with the substituter with `delete_at` which takes an index and `insert` takes an index and an object which is in our case the hash `dictionary[word.downase]`.

```Ruby
def bulk_tweet_shortener(tweets)
  tweets.map do |tweet|
    puts word_substituter(tweet)
  end
end
```
The `bulk_tweet_shortener` is to print the tweets after it is shorten.

```Ruby
def selective_tweet_shortener(tweet)
  tweet.length < 140 ? tweet : word_substituter(tweet)
end
```
This method is to check if the original tweet number of characters is less than 140 then it will print the original tweet otherwise we will implement the `word_substituter` on this tweet. I used a ternary operator in here.

```Ruby
def shortened_tweet_truncator(tweet)
  word_substituter(tweet).length > 140 ? "#{word_substituter(tweet)[0..135]} ..." : tweet
end
```
`shortened_tweet_truncator` is to check after the tweet is replaced by the substituter if it is still more than 140 characters then I make it 140 and then add an ellipsis otherwise just print the original tweet.

######  Monday 16th July
+ I am working on *__Hashketball__* lab which is the second lab in *__More on Hashes__*.

>* I finished working on 2 methods and still have 5 more to do.
>*  The 1st method is creating a nested hash with different data types.
```Ruby
def game_hash
  game_hash = {
    :home => {
      team_name: "Brooklyn Nets",
      colors: ["black", "white"],
      players: {
        "Alan Anderson" => {
          number: 0,
          shoe: 16,
          points: 22,
          rebounds: 12,
          assists: 12,
          steals: 3,
          blocks: 1,
          slam_dunks: 1
        },
        "Reggie Evans" => {
          number: 30,
          shoe: 14,
          points: 12,
          rebounds: 12,
          assists: 12,
          steals: 12,
          blocks: 12,
          slam_dunks: 7
        },
        "Brook Lopez" => {
          number: 11,
          shoe: 17,
          points: 17,
          rebounds: 19,
          assists: 10,
          steals: 3,
          blocks: 1,
          slam_dunks: 15
        },
        "Mason Plumlee" => {
          number: 1,
          shoe: 19,
          points: 26,
          rebounds: 12,
          assists: 6,
          steals: 3,
          blocks: 8,
          slam_dunks: 5
        },
        "Jason Terry" => {
          number: 31,
          shoe: 15,
          points: 19,
          rebounds: 2,
          assists: 2,
          steals: 4,
          blocks: 11,
          slam_dunks: 1
        }
      }
    },
    :away => {
      team_name: "Charlotte Hornets",
      colors: ["Turquoise", "Purple"],
      players: {
        "Jeff Adrien" => {
          number: 4,
          shoe: 18,
          points: 10,
          rebounds: 1,
          assists: 1,
          steals: 2,
          blocks: 7,
          slam_dunks: 2
        },
        "Bismak Biyombo" => {
          number: 0,
          shoe: 16,
          points: 12,
          rebounds: 4,
          assists: 7,
          steals: 7,
          blocks: 15,
          slam_dunks: 10
        },
        "DeSagna Diop" => {
          number: 2,
          shoe: 14,
          points: 24,
          rebounds: 12,
          assists: 12,
          steals: 4,
          blocks: 5,
          slam_dunks: 5
        },
        "Ben Gordon" => {
          number: 8,
          shoe: 15,
          points: 33,
          rebounds: 3,
          assists: 2,
          steals: 1,
          blocks: 1,
          slam_dunks: 0
        },
        "Brendan Haywood" => {
          number: 33,
          shoe: 15,
          points: 6,
          rebounds: 12,
          assists: 12,
          steals: 22,
          blocks: 5,
          slam_dunks: 12
        }
      }
    }
  }
end
```
>* The 2nd method is to retrieve data based on the given `player_name` as argument and to return the value of his `:points`.
```Ruby
def num_points_scored(player_name)
  result = nil
  game_hash.each do |location, team_data|
    team_data.each do |attribute, data|
      if attribute == :players
        data.each do |player, stats|
          if player == player_name
            stats.each do |k, v|
              if k == :points
                result = v
              end
            end
          end
        end
      end
    end
  end
  result
end
```

######  Tuesday 17th July
+ I worked on the rest of the lab *__Hashketball__*. It was tough and a bit confusing working with nested hashes but I've learned a lot through the process and I used `binding.pry` all the time to check which data I am working on at the time.
>* All I was thinking about at the beginning is to make my code work and then I can think about refactoring but I don't want my code to be confusing and not easy to understand at this stage.
```Ruby
def num_points_scored(player_name)
  result = nil
  game_hash.each do |location, team_data|
    team_data.each do |attribute, data|
      if attribute == :players
        data.each do |player, stats|
          if player == player_name
            stats.each do |k, v|
              if k == :points
                result = v
              end
            end
          end
        end
      end
    end
  end
  result
end
```
>* The following code is one of the methods I spent some time trying to solving it. One of the obstacles not updating max to the value while it is iterating to check the max value for `:shoe` and exiting the loop by `return stats[:rebounds]` so I had to create a variable and set it equal to `stats[:rebounds]` then return it at the end of the method.
```Ruby
def big_shoe_rebounds
  big_shoe = nil
  max = 0
  game_hash.each do |location, team_data|
    team_data.each do |attribute, data|
      if attribute == :players
        data.each do |player, stats|
          stats.each do |k, v|
            if k == :shoe && v > max
              max = v
              big_shoe = stats[:rebounds]
            end
          end
        end
      end
    end
  end
  big_shoe
end
```
>* Also `#player_numbers(team_name)` I spent time thinking about the conditional statement to connect the `team_name` and the `:players` together so I can access the team's players.
```Ruby
def player_numbers(team_name)
  player_numbers = []
  game_hash.each do |location, team_data|
    team_data.each do |attribute, data|
      if game_hash[location].values[0] == team_name && attribute == :players
        data.each do |player, stats|
          stats.each do |k, v|
            if k == :number
              player_numbers << v
            end
          end
        end
      end
    end
  end
  player_numbers
end
```
Check my Github repo *advanced-hashes-hashketball-prework* for the full version of this lab.

+ There are few bonus methods in this lab and I am going to work on it so I can learn and practice more.

+ I am doneeeee with this lab!!! I was a bit shocked with the Learn.co solution! How it is really fancy and short by using many helper methods and also `#fetch` that was the 1st time to see.
>* `fetch` returns a value from the hash for the given key.
>* If the key can't be found, there are several options:
>>* `h = { "a" => 100, "b" => 200 }`
>>* With no other arguments, it will raise an KeyError exception `h.fetch("z")` I will get an error msg.
>>* if default is given, then that will be returned `h.fetch("z", "go fish")` will return ``#=>"go fish"``
>>* if the optional code block is specified, then that will be run and its result returned `h.fetch("z") { |el| "go fish, #{el}"}` will return `#=>"go fish, z"`

+ Next I will be working on *__Programming Languages__* lab and practice more nested hashes and iteration.
