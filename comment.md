<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>react</title>
    <script src="https://unpkg.com/react@latest/dist/react.min.js" async></script>
    <script src="https://unpkg.com/react-dom@latest/dist/react-dom.min.js" async></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.21.1/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>

    <script async type="text/babel">
      function formatDate(date) {
        return date.toLocaleDateString();
      }
      function Comment(props) {
        return (
          <div className="Comment">
            <div className="UserInfo">
              <img className="Avator"
                src={props.author.avatarUrl}
                alt={props.author.name} />
              <div className="UserName">
                {props.author.name}
              </div>
            </div>
            <div className="Comment-text">
              <textarea className="comment-textarea" rows="10" cols="40">
                {props.text}
              </textarea>
            </div>
            <div className="Comment-date">
              {formatDate(props.date)}
            </div>
          </div>
          );
      }
      const commentObjectModel = {
        date: new Date(),
        text: 'React is cool',
        author: {
          name: 'Emrul Hasan Zawad',
          avatarUrl: 'http://placekitten.com/g/64/64'
        }
      }
      const commentObjectModel2 = {
        date: new Date(),
        text: 'Nayeem Anam is a chemist',
        author: {
          name: 'Nayeem Anam',
          avatarUrl: 'http://placekitten.com.s3.amazonaws.com/homepage-samples/96/140.jpg'
        }
      }
      function Bundle(props) {
        return (
            <div>
              <h4> {props.title} </h4>
              <Comment
                date={commentObjectModel.date}
                text={commentObjectModel.text}
                author={commentObjectModel.author} />
              <Comment
                date={commentObjectModel2.date}
                text={commentObjectModel2.text}
                author={commentObjectModel2.author} />
            </div>
          );
      }
      ReactDOM.render(
        <Bundle title="ReactCommentSection" />, document.getElementById('root')
      );
    </script>
  </body>
</html>
