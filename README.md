const express=require('express')
const mangoose=rrequire('mongoose')
const cors=require('cors')
const UserModel=require('./models/Users')

const app = express()
app.use(cors())
app.use(express.json())

mongoose.connect("mongodb+srv://Sandeep41800:9T8jyUkQOc7S4bEx@cluster0.ppgo7xs.mongodb.net/Popcorn?retryWrites=true&w=majority")

app.get('/getUsers',(req,res)=>{
    UserModel.find()
    .then(users=>res.json(users))
    catch(app=> res.json(err))
})
app.listen(3001,() =>{
    console.log("Server is running")
})
