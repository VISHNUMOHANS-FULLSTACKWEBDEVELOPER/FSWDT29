# FSWDT29
Day29
<!DOCTYPE html>
<html>
    <head>
        <title>Js build Project</title>
          <!-- Font awesome icons -->
    <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css"
    integrity="sha512-KfkfwYDsLkIlwQp6LFnl8zNdLGxu9YAA1QvwINks4PhcElQSvqcyVLLD9aMhXd13uQjoXtEKNosOWaZqXgel0g=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  />
        <!-- styles -->
        <link href="./index.css" rel="stylesheet"/>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">

    </head>
    <body onload="loadIntialData">
<!-- Small Screen size buton -->
      <div class="add__new__button__only d-md-none ">
       <button class="btn btn-outline-primary align items-center gap-3" type="submit"data-bs-toggle="modal" data-bs-target="#addModal">
        <i class="fa-solid fa-plus mr-4 "></i> Add new item
       </button>
      </div>
<!-- open task model -->
<div class="modal fade" id="showTask" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Task Details...</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body task__modal__body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <!-- <button type="button" class="btn btn-primary">Save changes</button> -->
      </div>
    </div>
  </div>
</div>

<!-- Modal -->
      <div class="modal fade" id="addModal" tabindex="-1" aria-labelledby="addModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="addModal">Add New Task</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <form>
          <!-- img -->
          <div class="mb-3">
            <label for="imgurl" class="form-label">Image Url</label>
            <input type="url" class="form-control" id="url" aria-describedby="imgurl" placeholder="https://vishnumohan/img">
            <div id="imgurl" class="form-text" >This is an optional field for you</div>
          </div>
          <!-- title -->
          <div class="mb-3">
            <label for="Tilte" class="form-label">Task Title</label>
            <input type="text" class="form-control" id="taskTitle" aria-describedby="TaskTitle" placeholder="TaskTitle" required>
          </div>
          <!-- Task type -->
          <div class="mb-3">
            <label for="Task Type" class="form-label">Task Type</label>
            <input type="text" class="form-control" id="tags" aria-describedby="TasktypeDesc" placeholder="TaskType"required>
          </div>
        <!-- Task Description -->
         <div>
          <label for="TaskDescription" class="form-label">Text description</label>
          <textarea
             type="text" class="form-control" id="taskDescription"  placeholder="TaskDescription" rows="3" required
          ></textarea>
        </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="submit" class="btn btn-primary"  onclick=" handleSubmit()">Save changes</button>
      </div>
    </div>
  </div>
      </div>
<!-- Nav Bar -->
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
            <div class="container-fluid">
              <a class="navbar-brand" href="#">Js project</a>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                  <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                      <a class="nav-link active" aria-current="page" href="#">Home</a>
                    </li>
                    </ul>
                </div>
                      <button class="btn btn-outline-primary align items-center gap-3" type="submit"data-bs-toggle="modal" data-bs-target="#addModal">
                        <i class="fa-solid fa-plus mr-4 "></i> Add new item
                  </button>
              </div>
            </div>
          </nav>
          <div class="container">
            <section class="mt-4">
              <div class="row justify content-center">
                <div class=".col-md-6">
                   <div class="input-group flex-nowrap shadow-lg rounded">
                    <input type="search"class="form-control" placeholder="Search your ask here"aria-label="Search task" aria-describedby="addon-wrapping"
                    <span class="input-group-text" id="addon-wrapping">
                      <i class="fas fa-search m-2"></i>
                    </span>
                  </div>
                </div>
               <!-- <div class=".col-md-6">
                  
                </div> -->
              </div>
            </section>
            <section class="mt-4">
              <!-- cards -->
               <div class="row task__contents"></div>
            </section>
          </div>




<!-- Scripts -->
        <script src="./index.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
        <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.min.js" integrity="sha384-0pUGZvbkm6XF6gxjEnlmuGrJXVbNuzT9qBBavbLwCsOGabYfZo0T0to5eqruptLy" crossorigin="anonymous"></script>

    </body>
</html>
js
// var state={
//      tasklist:[
//         {
//         imgUrl:"",
//         taskdetails:"",
//         tasktype:"",
//         taskdescription:"",
//         },
//         {
//          imgUrl:"",
//          taskdetails:"",
//          tasktype:"",
//          taskdescription:"",
//         },
//         {
//          imgUrl:"",
//          taskdetails:"",
//          tasktype:"",
//          taskdescription:"",
//          },
//         {
//         imgUrl:"",
//         taskdetails:"",
//         tasktype:"",
//         taskdescription:"",
//         },
//     ],
// };
const state={
    tasklist:[]
};
// DOM operations
const taskcontents= document.querySelector(".task__contents");
const taskmodal= document.querySelector(".task__modal__body");
// console.log(taskcontents);
// console.log(taskmodal);


// Template for card section
const htmltaskcontent=({id,type,title,description,url})=>{`
    <div class='col-md-6 col-lg-4 mt-3' id=${id}>
      <div class='card shadow-sm  task__card__header'>
      <div class='card-header d-flex justify content-end task__card__header'>
      <button type='button' class='btn outline-primary mr-1.5' name='${id}' >
      <i name='${id}'class='fas fa-pencil-alt'></i>
      </button>
      <button type='button' class='btn outline-danger mr-1.5' name='${id}' >
      <i name='${id}'class='fas fa-trash-alt'></i>
      </button>
        </div>
        <div class='card__body'>
        ${
            url &&
            `<img src=${url} atl='Card Image' width=100% class='card-img-top md-3 rounded-lg'/>
            <h4 class="card-title">${title}</h4>
            <p class="description trim-3-lines">${description}</p>
            <div class='tags text-white d-flex flex-wrap'>
            <span class='badge bg-primary m-1'></span>
            </div>
            <div>
            <button type='button' class='btn btn-primary float-right'data-bs-toggle="modal" data-bs-target="#showTask">>Open task</button>
            </div>
        `}
        </div>
    </div>
    </div>
    `};
    // Modal body on click open task
    const task__modal__body=({id,type,title,description,url})=>
    {
        const date=new Date(parseInt(id));
        return`
        <div id=$(id)>
        ${
            url &&
            `<img src=${url} atl='Card Image' width=100% class='card-img-top md-3 rounded-lg'/>`
         }
        <strong class='text-muted text-sm'>Created on:${date.Todatestring()}</strong>
        <h2 class='my-3'>${title}</h2>
        <p class='text-muted'>${description}</p>
        </div>`
    };


    // We are storing the data in the local sorage and converting the json > string
    const updateLocalStorage=()=>{
  localStorage.getItem(
    'tasky',JSON.stringify({tasks:state.tasklist,})
  );
    };
    // We are displaying the data in the local sorage and converting the string > json
    const loadIntialData=()=>{
      const localStoragecopy=JSON.parse(localStorage.tasklist);

      if(localStoragecopy)  state.tasklist=localStorage.tasklist;

      state.tasklist.map(date)=()=>{
        taskcontents.insertAdjacentHTML("beforeend",htmltaskcontent(date));
      }
    };
    // we need o confirm that a single&same card operation at a time
    // At the same  we need to save the updated data
    const handleSubmit=(event)=>{
      const id=`${Date.now()}`;
      const input={
        url:document.getElementById("url").value, 
        title:document.getElementById("taskTitle").value,   
        type:document.getElementById("tags").value,    
        description:document.getElementById("taskDescription").value      
      };
      if(input.title=== ""||input.type=== ""|| input.description=== ""){
        return alert("pls fill the required field;");
      }

      taskcontents.insertAdjacentHTML("beforeend",htmltaskcontent({...input,id}));
       state.tasklist.push({...input,id});
    updateLocalStorage();
    };
    // spread operator
    //  const obj={
    //  name:"vishnu" ,age:1}
    //  undefined
    //  console.log(obj);
    //  VM290:1 {name: 'vishnu', age: 1}
    //  undefined
    //  console.log({obj});
    //  VM340:1 {obj: {…}}obj: {name: 'vishnu', age: 1}age: 1name: "vishnu"[[Prototype]]: Object[[Prototype]]: Objectconstructor: ƒ Object()hasOwnProperty: ƒ hasOwnProperty()isPrototypeOf: ƒ isPrototypeOf()propertyIsEnumerable: ƒ propertyIsEnumerable()toLocaleString: ƒ toLocaleString()toString: ƒ toString()valueOf: ƒ valueOf()__defineGetter__: ƒ __defineGetter__()__defineSetter__: ƒ __defineSetter__()__lookupGetter__: ƒ __lookupGetter__()__lookupSetter__: ƒ __lookupSetter__()__proto__: (...)get __proto__: ƒ __proto__()set __proto__: ƒ __proto__()
    //  undefined
    //  console.log({...obj});
    //  VM415:1 {name: 'vishnu', age: 1}
    //  undefined
    //  console.log({...obj,designation:"student"});
    //  VM545:1 {name: 'vishnu', age: 1, designation: 'student'}
