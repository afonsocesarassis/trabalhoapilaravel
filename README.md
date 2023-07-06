# trabalhoapilaravel

route::get('/tasks', [TaskController::class, 'index']);
esse get procura todas as tarefas do banco de dados.

route::post('/tasks', [TaskController::class, 'store']);
Esse post cria as tarefas.

route::get('/tasks/{id}', [TaskController::class, 'show']);
esse get busca apenas uma tarefa, procurada pelo id dela.


route::put('/tasks/{id}', [TaskController::class, 'update']);
esse put atualiza a tarefa que foi buscada pelo id.

route::delete('/tasks/{task}', [TaskController::class, 'destroy']);
deleta a tarefa que for procurada.

funçoes

 public function index(){
      $tasks = Task::all();
      return response()->json($tasks);
    }
    
   essa função vai mostrar todas as tarefas.
_______________
public function store(Request $request){
        $task = Task::create($request->all());
        return response()->json($task, 201);
    }

essa função vai criar a tarefa.

_______________
public function show($id)
{
        $task = Task::find($itask);
        return response()->json($task);
    }

essa função procura a tarefa pelo id dela.

__________________
public function update(Request $request, $id){
        $task = Task::find($id);
        $task->status = $request->input('status');
        $task->title = $request->input('tdescription');
        $task->save();
        return response()->json($task);
    }

essa função atualiza a tarefa.

______________
public function destroy(Task $task){
        $task->delete();
        return response()->json(null, 204);
    }

essa função apaga a tarefa.









