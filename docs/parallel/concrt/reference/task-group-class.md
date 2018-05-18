La classe `task_group` représente une collection de travail parallèle qui peut être attendue ou annulée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class task_group;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[task_group](#ctor)|Surchargé. Construit un nouveau `task_group` objet.|  
|[~ task_group, destructeur](#dtor)|Détruit un objet `task_group`. Vous devez appeler la la `wait` ou `run_and_wait` méthode sur l’objet avant l’exécution du destructeur, sauf si le destructeur s’exécute en tant que le résultat de la pile de déroulement en raison d’une exception.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[cancel](#cancel)|Permet un meilleur effort pour annuler la sous-arborescence de travail rattachée à ce groupe de tâches. Chaque tâche planifiée sur le groupe de tâches sera annulée de manière transitive si possible.|  
|[is_canceling](#is_canceling)|Indique si le groupe de tâches est actuellement en cours d’annulation à l’appelant. Cela n’indique pas nécessairement que le `cancel` méthode a été appelée sur le `task_group` objet (bien que ce cas la méthode retourne `true`). Il peut arriver que le `task_group` objet s’exécute en ligne et un groupe de tâches supplémentaire en haut dans l’arborescence de travail a été annulé. Dans tels cas où l’exécution peut déterminer à l’avance que cette annulation passera via cet `task_group` objet, `true` s’affichera également.|  
|[run](#run)|Surchargé. Planifie une tâche sur le `task_group` objet. Si un `task_handle` objet est passé en tant que paramètre à `run`, l’appelant est chargé de gérer la durée de vie de la `task_handle` objet. La version de la méthode qui accepte une référence à un objet de fonction comme un paramètre implique l’allocation de tas au sein du runtime qui peut être moins performante que l’utilisation de la version qui prend une référence à un `task_handle` objet. La version qui prend le paramètre `_Placement` amène la tâche à être favorise l’exécution à l’emplacement spécifié par ce paramètre.|  
|[run_and_wait](#run_and_wait)|Surchargé. Planifie une tâche à exécuter inline dans le contexte d’appel avec l’assistance de la `task_group` objet pour la prise en charge complète de l’annulation. La fonction attend ensuite que tout le travail sur le `task_group` objet est terminée ou annulé. Si un `task_handle` objet est passé en tant que paramètre à `run_and_wait`, l’appelant est chargé de gérer la durée de vie de la `task_handle` objet.|  
|[attente](#wait)|Attend que tout le travail sur le `task_group` objet est terminée ou annulé.|  
  
## <a name="remarks"></a>Notes  
 Contrairement aux très restreinte `structured_task_group` (classe), la `task_group` classe est une construction beaucoup plus générale. Il n’a pas de restrictions décrites par [structured_task_group](structured-task-group-class.md). `task_group` objets en toute sécurité peuvent être utilisées sur les threads et utilisées dans un format libre. L’inconvénient de la `task_group` construction est qu’il ne peut pas effectuer, ainsi que les `structured_task_group` construire pour les tâches qui exécutent des petites quantités de travail.  
  
 Pour plus d’informations, consultez [parallélisme des tâches](../task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `task_group`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="cancel"></a> Annuler 

 Permet un meilleur effort pour annuler la sous-arborescence de travail rattachée à ce groupe de tâches. Chaque tâche planifiée sur le groupe de tâches sera annulée de manière transitive si possible.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [annulation](../cancellation-in-the-ppl.md).  
  
##  <a name="is_canceling"></a> is_canceling 

 Indique si le groupe de tâches est actuellement en cours d’annulation à l’appelant. Cela n’indique pas nécessairement que le `cancel` méthode a été appelée sur le `task_group` objet (bien que ce cas la méthode retourne `true`). Il peut arriver que le `task_group` objet s’exécute en ligne et un groupe de tâches supplémentaire en haut dans l’arborescence de travail a été annulé. Dans tels cas où l’exécution peut déterminer à l’avance que cette annulation passera via cet `task_group` objet, `true` s’affichera également.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une indication précisant si le `task_group` objet est en cours d’annulation (ou qu’il est garanti être peu de temps).  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [annulation](../cancellation-in-the-ppl.md).  
  
##  <a name="run"></a> Exécuter 

 Planifie une tâche sur le `task_group` objet. Si un `task_handle` objet est passé en tant que paramètre à `run`, l’appelant est chargé de gérer la durée de vie de la `task_handle` objet. La version de la méthode qui accepte une référence à un objet de fonction comme un paramètre implique l’allocation de tas au sein du runtime qui peut être moins performante que l’utilisation de la version qui prend une référence à un `task_handle` objet. La version qui prend le paramètre `_Placement` amène la tâche à être favorise l’exécution à l’emplacement spécifié par ce paramètre.  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Function`  
 Le type de l’objet de fonction qui sera appelé pour exécuter le corps de la poignée de la tâche.  
  
 `_Func`  
 Fonction qui sera appelée pour appeler le corps de la tâche. Cela peut être une expression lambda ou un autre objet qui prend en charge une version de l’opérateur d’appel de fonction avec la signature `void operator()()`.  
  
 `_Placement`  
 Une référence à l’emplacement où la tâche est représentée par la `_Func` paramètre doit s’exécuter.  
  
 `_Task_handle`  
 Handle vers le travail planifié. Notez que l’appelant est responsable de la durée de vie de cet objet. Le runtime continuera à attendre qu’il live jusqu'à ce que le `wait` ou `run_and_wait` méthode a été appelée sur ce `task_group` objet.  
  
### <a name="remarks"></a>Notes  
 Le runtime planifie la fonction de travail fournie pour s’exécuter à une date ultérieure, qui peut être après le retour de la fonction appelante. Cette méthode utilise un [task_handle](task-handle-class.md) objet à conserver une copie de la fonction de travail fournie. Par conséquent, toute modification d’état qui se produire dans un objet de fonction que vous passez à cette méthode n’apparaîtront pas dans votre copie de cet objet de fonction. En outre, assurez-vous que la durée de vie de tous les objets que vous passez par le pointeur ou par référence à la fonction de travail reste valide jusqu’au retour de la fonction de travail.  
  
 Si le `task_group` résulte de la pile de déroulement à partir d’une exception, il est inutile garantir qu’un appel a été effectué sur le `wait` ou `run_and_wait` (méthode). Dans ce cas, le destructeur annulera et attendez que la tâche représentée par le `_Task_handle` paramètre pour terminer.  
  
 La méthode lève un [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) exception si la tâche gérer donné par le `_Task_handle` paramètre a déjà été planifié sur un objet de groupe de tâches via la `run` (méthode) et il y a eu aucune appel d’intervention à la `wait` ou `run_and_wait` méthode sur ce groupe de tâches.  
  
##  <a name="run_and_wait"></a> run_and_wait 

 Planifie une tâche à exécuter inline dans le contexte d’appel avec l’assistance de la `task_group` objet pour la prise en charge complète de l’annulation. La fonction attend ensuite que tout le travail sur le `task_group` objet est terminée ou annulé. Si un `task_handle` objet est passé en tant que paramètre à `run_and_wait`, l’appelant est chargé de gérer la durée de vie de la `task_handle` objet.  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Function`  
 Le type de l’objet de fonction qui sera appelé pour exécuter le corps de la tâche.  
  
 `_Task_handle`  
 Un handle vers la tâche qui sera exécutée inline sur le contexte d’appel. Notez que l’appelant est responsable de la durée de vie de cet objet. Le runtime continuera à attendre qu’il vive jusqu'à ce que le `run_and_wait` méthode termine son exécution.  
  
 `_Func`  
 Fonction qui sera appelée pour appeler le corps du travail. Cela peut être une expression lambda ou un autre objet qui prend en charge une version de l’opérateur d’appel de fonction avec la signature `void operator()()`.  
  
### <a name="return-value"></a>Valeur de retour  
 Indique si l’attente a été satisfaite ou le groupe de tâches a été annulé en raison d’une opération d’annulation explicite ou d’une exception est levée à partir d’une de ses tâches. Pour plus d’informations, consultez [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Notes  
 Notez qu’une ou plusieurs des tâches planifiées pour cet `task_group` objet peut-être s’exécuter inline dans le contexte d’appel.  
  
 Si un ou plusieurs des tâches planifiées pour cet `task_group` objet lève une exception, le runtime sélectionne une exception de ce type de son choix et la propager en dehors de l’appel à la `run_and_wait` (méthode).  
  
 Au retour de la `run_and_wait` méthode sur un `task_group` de l’objet, le runtime réinitialise l’objet dans un état cohérent où il peut être réutilisé. Cela inclut le cas où le `task_group` objet a été annulé.  
  
 Dans le chemin d’exécution non exceptionnel, vous avez une autorisation d’appeler cette méthode ou la `wait` méthode avant le destructeur de la `task_group` s’exécute.  
  
##  <a name="ctor"></a> task_group 

 Construit un nouveau `task_group` objet.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_CancellationToken`  
 Un jeton d’annulation à associer à ce groupe de tâches. Le groupe de tâches sera annulé lorsque le jeton est annulé.  
  
### <a name="remarks"></a>Notes  
 Le constructeur qui accepte un jeton d’annulation crée un `task_group` qui sera annulée lors de l’annulation de la source associée au jeton. En fournissant un jeton d’annulation explicite isole également de participer à une annulation implicite à partir d’un groupe parent avec un jeton différent ou aucun jeton de ce groupe de tâches.  
  
##  <a name="dtor"></a> ~ task_group 

 Détruit un objet `task_group`. Vous devez appeler la la `wait` ou `run_and_wait` méthode sur l’objet avant l’exécution du destructeur, sauf si le destructeur s’exécute en tant que le résultat de la pile de déroulement en raison d’une exception.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>Notes  
 Si le destructeur s’exécute en tant que le résultat d’une exécution normale (par exemple, pas déroulement de pile en raison d’une exception) et ne le `wait` ni `run_and_wait` a été appelée, le destructeur peut lever une [missing_wait](missing-wait-class.md) exception.  
  
##  <a name="wait"></a> attente 

 Attend que tout le travail sur le `task_group` objet est terminée ou annulé.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Indique si l’attente a été satisfaite ou le groupe de tâches a été annulé en raison d’une opération d’annulation explicite ou d’une exception est levée à partir d’une de ses tâches. Pour plus d’informations, consultez [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Notes  
 Notez qu’une ou plusieurs des tâches planifiées pour cet `task_group` objet peut-être s’exécuter inline dans le contexte d’appel.  
  
 Si un ou plusieurs des tâches planifiées pour cet `task_group` objet lève une exception, le runtime sélectionne une exception de ce type de son choix et la propager en dehors de l’appel à la `wait` (méthode).  
  
 Appel de `wait` sur un `task_group` objet réinitialise à un état propre sur lequel il peut être réutilisé. Cela inclut le cas où le `task_group` objet a été annulé.  
  
 Dans le chemin d’exécution non exceptionnel, vous avez une autorisation d’appeler cette méthode ou la `run_and_wait` méthode avant le destructeur de la `task_group` s’exécute.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [structured_task_group, classe](structured-task-group-class.md)   
 [task_handle, classe](task-handle-class.md)