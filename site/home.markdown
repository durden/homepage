<p class="intro">
My name is <a href="#">Luke Lee</a>. I <a href="#">write</a> and
<a href="#">talk</a> about software.
</p>
<ul class="posts">
</ul>

<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>

<script type="text/javascript">
    $(document).ready(function () {
        $.getJSON('http://codrspace.com/api/post/' +
            '?format=jsonp&username=durden&' +
            'api_key=c139439a4d682d2db84a8d603eddb5c38c56d8e5&callback=?',
            function(json) {
                console.log(json);
                html = '<ul>';

                for (var post in json.objects) {
                    html += '<li><a href="' + json.objects[post]['url'] + '">' +
                            json.objects[post]['title'] + '</a></li>';
                }

                html += '</ul>';
            $('.posts').html(html);
        });
    });
</script>
