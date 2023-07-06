# trabalhoapilaravel

route::get('/tasks', [TaskController::class, 'index']);


route::post('/tasks', [TaskController::class, 'store']);


route::get('/tasks/{id}', [TaskController::class, 'show']);



route::put('/tasks/{id}', [TaskController::class, 'update']);


route::delete('/tasks/{task}', [TaskController::class, 'destroy']);


funçoes

 public function index(){
      $tasks = Task::all();
      return response()->json($tasks);
    }
    

_______________
public function store(Request $request){
        $task = Task::create($request->all());
        return response()->json($task, 201);
    }



_______________
public function show($id)
{
        $task = Task::find($itask);
        return response()->json($task);
    }

__________________
public function update(Request $request, $id){
        $task = Task::find($id);
        $task->status = $request->input('status');
        $task->title = $request->input('tdescription');
        $task->save();
        return response()->json($task);
    }



______________
public function destroy(Task $task){
        $task->delete();
        return response()->json(null, 204);
    }











