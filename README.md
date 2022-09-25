# MongoDB-Assignment
//****Insert the 10 sample blogs into the blogs collection****//
db.BlogsDB.insertMany([
    {
       

//***********- **Write the following queries and add them to the README**:******//

// - Insert a new blog into the collection //
db.BlogsDB.insertOne(
    // db.BlogsDB.insertMany([])
    
    

//*****************Find one blog by author:**************************//
db.BlogsDB.find({
    _id: ObjectId("632b5cb4f1e5b6a0543ff3c7")
    })




//****************Find all blogs whose objectId is greater than 5******************//
db.BlogsDB.find([
    ObjectId: {
        $gt: 5
    }



//****************Find all blogs whose createdAt is after April 1, 2022****************//
db.BlogsDB.find({
    createdAt:{
    $gt: new Date(“4/1/22”)
    }

 // No records found



//*******************PART 2******************* */
//Write the following queries and add them to the README:
// ************************Find all blogs where the field lastModified exists *************************//
db.BlogsDB.find({
lastModified:{
}
    })
 



//***************************Find all blogs where the createdAt type is a date****************************//
db.BlogsDB.find({
    createdAt:{
    $eq:  Date(“ ”)
    }


//***********************Find a blog with a specific phrase in the text************************** */
db.BlogsDB.findOne({})


//*********************************Find all blogs that have "qui" in the categories array*/
db.BlogsDB.find({
    categories:{
    $eq:  [“qui”]
    }
    
    
    
    
   //*******************PART 3******************* */
// - Write the following queries and add them to the README:
//**************************Find all blogs in which the lastModified does not exist and set it*********************************
db.BlogsDB.find({
    lastModified:{
    $exist: false
    }
})
//From now on, all the following queries should update lastModified to be the current datetime ***********************************


// ********************** Find all blogs created after May 2022 and add "lorem" as a new category in the categories array********************** 
db.BlogsDB.find({
    DateAdded:{
        $gt:  Date(“May 2022”)
        })

db.Blogs.updateOne({
    id: "categories"
},{
    $set:{ categories: "lorem"
 }
})

//**********************Find all blogs that have the category "voluptas" and pull "voluptas" from the categories**********************
db.BlogsDB.find({
    categories:{
        $eq:  categories["voluptas"]
    },{
        $pull: {
            categories: ["voluptas"]
        }
    })
// **********************Find all blogs with "corrupti" in the categories and delete those blogs**********************
db.BlogsDB.find({
    categories:{
        $eq:  categories["corrupti"]
    },{
        db.BlogsDB.deleteOne({
            id: "corrupti"
        })
    })   
    
    
