# virusConfinement
APP.JS
const express=require('express');
const app =express();
const hbs=require('hbs')
const bodyParser=require('body-parser')

app.use(bodyParser.urlencoded({extended:true}))
app.set('view engine','hbs')


app.get('/',function(req,res,next){
res.render('login',{})
});/// un app.get vers le meme chemin justement le get pour recupere la page avec ce qui a remplir. 

app.post('/',function(req,res,next){
   console.log('req.body=',req.body.email)
   if(req.body.email==='massi.messalti@gmail.com' && req.body.password==='massi'){
    res.send(`Formulaire soumis l'email :${req.body.email} password:${req.body.password}`);
   }else{
       res.send('veuillez vous enregistrer')
   }
  
});// dans ce cas la on va submit le form et on sera redériger vers cette page, on peut avoir un app.get vers le meme chemin justement le get pour recupere la page avec ce qui a remplir. 

app.listen(3000,()=>console.log('je suis sur le serveur'))





Login.hbs
<form action="/" method="POST">
    <label for="email">Email</label>
    <input type="email" id="email" name="email">

    <label for="password">Password</label>
    <input type="password" id="password" name="password">
    <button>submit</button>
</form>

