# Thursday, 18-Jan-18 12:00:01 UTC  
set DF labels  

    labels = ['subreddit', 'title', 'id', 'url', 'author', 'body']
    post_frame = pd.DataFrame(posts_tmp, columns=labels)
