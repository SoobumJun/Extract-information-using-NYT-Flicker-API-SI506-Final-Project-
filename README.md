# final_project_SI506
* what does my project do?

#######
Using 5 keywords that were extracted from the NYT articles' abstract (which are the longest words in each article), I searced 20 photos for each keyword (total 100 photos) in Flickr.
I used New York Times ArticleSearch API to search and get information about articles. I also used Flickr API to search and get the data about the photo. 

#######


* What Python modules must be pip installed in order to run your submission? List them ALL (e.g. including requests, requests_oauthlib... anything someone running it will need!). Note that your project must run in Python 3.

########
requests
json 
########
 


* Explain SPECIFICALLY how to run your code. We should very easily know, after reading this:
    
#########
 the file we need to run is SI506_final_Soobumjun.py
########


* Where can we find all of the project technical requirements in your code? Fill in with the requirements list below.

REQUIREMENTS LIST:
* Get and cache data from 2 REST APIs (list the lines where the functions to get & cache data begin and where they are invoked):
		#1st REST API
			- Function     : Line 50
			- Cache   	   : Line 78(write) Line 53(read)
			- Function call: Line 260
		#2nd REST API
			- Function     : Line 150
			- Cache        : Line 177(write) Line 152(read)
			- Function call: Line 250
		#3rd REST API
			- Function     : Line 110
			- Cache        : Line 117(write) 
			- Function call: Line 220


* If you relied upon FB data and did not cache it, say so here:
* Define at least 2 classes, each of which fulfill the listed requirements:
		#1st Class: Line 9
		#2nd Class: Line 32


* Create at least 1 instance of each class:
		#1st Class: Line 226   //Article(tup[0], tup[1], tup[2], tup[3])
		#2nd Class: Line 256   //Photo(tup[0], tup[1], tup[2], tup[3])


* Invoke the methods of the classes on class instances:
		#Line 242  //article_insts_list[i].find_longest_word()
		#Line 260  //photo.request_more_photo_info()


* At least one sort with a key parameter:
		#1st sorting: Line 229  //sorted(article_insts_list, key=lambda article: (-article.num_of_keywords, article.headline))
		#2nd sorting: Line 264  //sorted(photo_insts_list, key=lambda photo: photo.num_of_tags)


* Define at least 2 functions outside a class (list the lines where function definitions begin):
		#1st function: Line 101  //def params_unique_combination(baseurl, params_d, private_keys=["api_key"]):
		#2nd function: Line 110  //def get_article_data(param_code):
		#3rd function: Line 123  //def filter_article_data(file_name):


* Invocations of functions you define:
		#1st function: Line 167  //unique_ident = params_unique_combination(base_url, params_d)
		#2nd function: Line 220  //get_article_data('google')  
		#3rd function: Line 221  //article_info_tups_list = filter_article_data(NYT_CACHE_FNAME) 
* Create a readable file:
		#SOOBUM_README_506F17_FinalProject.txt
END REQUIREMENTS LIST

* Put any citations you need below. If you borrowed code from a 506 problem set directly, or from the textbook directly, note that. If you borrowed code from a friend/classmate or worked in depth with a friend/classmate, note that. If you borrowed code from someone else's examples on a website, note that.
		# All the code are referenced from the class materials, but modified that fit to this assignments.
		# Also, Jaeun you from University of Illinois, Chicago student helped and gave me insight to make a search on Flickr.

* Explain in a couple sentences what should happen as a RESULT of your code running: what CSV or text file will it create? What information does it contain? What should we expect from it in terms of how many lines, how many columns, which headers...?
		# In console, it will show a list of articles that is searched in NYT website. It includes headline, url, abstract and keywords.
		# Also, it will show the information of the photo that we can get from flickr about the keywords that we got from the previos step. It gives informations of 20 photos for each keyword (total 100 photos).This informations will be saved as photo_information.csv file (columes: Photo title, Username, Tags, Number of Tags, Date / 100 rows of data)
