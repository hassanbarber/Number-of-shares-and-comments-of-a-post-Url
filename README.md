# Number-of-shares-and-comments-of-a-post-Url
Number of shares and comments of a post Url
var postUrl = location.href;

var get_fbcount = function() {

  $.getJSON('https://graph.facebook.com/' + postUrl, function(data) {

    var commentcount = data.share.comment_count;

    console.log(data);

    if (commentcount) {

      $('.comment_count').append(commentcount);

    } else {

      $('.comment_count').append(0);

    }

 var sharecount = data.share.share_count;

    console.log(data);

    if (sharecount) {

      $('.share_count').append(sharecount);

    } else {

      $('.share_count').append(0);

    }

  });

};

get_fbcount();
