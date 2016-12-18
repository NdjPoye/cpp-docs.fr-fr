---
title: "Utilisation des objets accelerator et accelerator_view | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des objets accelerator et accelerator_view
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la [accelerator](../../parallel/amp/reference/accelerator-class.md) et [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) des classes pour spécifier le périphérique ou l’émulateur pour exécuter votre code C++ AMP. Un système peut avoir plusieurs périphériques ou les émulateurs qui diffèrent par la quantité de mémoire, prise en charge de la mémoire partagée, débogage de prise en charge ou prise en charge de la double précision. C++ Accelerated les Massive Parallelism (C++ AMP) fournit des API que vous pouvez utiliser pour examiner les accélérateurs disponibles, définir un comme la valeur par défaut, spécifiez plusieurs accelerator_views différents pour plusieurs appels à parallel_for_each et effectuer des tâches de débogage spéciales.  
  
## <a name="using-the-default-accelerator"></a>À l’aide de l’accélérateur par défaut  
 Le runtime C++ AMP choisit un accélérateur par défaut, sauf si vous écrivez du code permettant de sélectionner une seule. Le runtime sélectionne l’accélérateur par défaut comme suit :  
  
1.  Si l’application s’exécute en mode débogage, un accélérateur qui prend en charge le débogage.  
  
2.  Dans le cas contraire, l’accélérateur qui est spécifié par la variable d’environnement CPPAMP_DEFAULT_ACCELERATOR si elle est définie.  
  
3.  Dans le cas contraire, un périphérique non émulé.  
  
4.  Dans le cas contraire, le périphérique ayant la plus grande quantité de mémoire disponible.  
  
5.  Dans le cas contraire, un périphérique qui n’est pas attaché à l’affichage.  
  
 En outre, le runtime spécifie un `access_type` de `access_type_auto` pour l’accélérateur par défaut. Cela signifie que l’accélérateur par défaut utilise la mémoire partagée si elle est prise en charge et si ses caractéristiques de performance (la bande passante et la latence) sont connus pour être le même que de mémoire dédiée (non partagé).  
  
 Vous pouvez déterminer les propriétés de l’accélérateur par défaut en créant l’accélérateur par défaut et en examinant ses propriétés. L’exemple de code suivant imprime le chemin d’accès, la quantité de mémoire de l’accélérateur, prise en charge de la mémoire partagée, prise en charge double précision et la prise en charge de double précision limitée de l’accélérateur par défaut.  
  
```cpp  
 
void default_properties() {  
    accelerator default_acc;  
    std::wcout <<default_acc.device_path <<"\n";  
    std::wcout <<default_acc.dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
}  
 
```  
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>Variable d’environnement CPPAMP_DEFAULT_ACCELERATOR  
 Vous pouvez définir la variable d’environnement CPPAMP_DEFAULT_ACCELERATOR pour spécifier le `accelerator::device_path` de l’accélérateur par défaut. Le chemin d’accès dépend du matériel. Le code suivant utilise le `accelerator::get_all` de fonction pour récupérer la liste des accélérateurs de disponible, puis affiche le chemin d’accès et les caractéristiques de chaque raccourci.  
  
```cpp  
 
void list_all_accelerators()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
for (int i = 0; i <accs.size();

i++) {  
    std::wcout <<accs[i].device_path <<"\n";  
    std::wcout <<accs[i].dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
 }  
}  
 
```  
  
## <a name="selecting-an-accelerator"></a>Sélection d’un accélérateur  
 Pour sélectionner un accélérateur, utilisez la `accelerator::get_all` méthode pour récupérer la liste des accélérateurs de disponibles et sélectionnez une option en fonction de ses propriétés. Cet exemple montre comment sélectionner l’accélérateur qui a le plus de mémoire :  
  
```cpp  
 
void pick_with_most_memory()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator acc_chosen = accs[0];  
    for (int i = 0; i <accs.size();

i++) {  
    if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {  
    acc_chosen = accs[i];  
 }  
 }  
 
    std::wcout <<"The accelerator with the most memory is "    
 <<acc_chosen.device_path <<"\n"  
 <<acc_chosen.dedicated_memory <<".\n";  
}  
 
```  
  
> [!NOTE]
>  Parmi les accélérateurs qui sont retournés par `accelerator::get_all` est l’accélérateur du processeur. Vous ne pouvez pas exécuter du code sur l’accélérateur CPU. Pour exclure l’accélérateur CPU, comparez la valeur de la [chemin_unité](../Topic/accelerator::device_path%20Data%20Member.md) propriété de l’accélérateur qui est retourné par `accelerator::get_all` avec la valeur de la [accelerator::cpu_accelerator](../Topic/accelerator::cpu_accelerator%20Data%20Member.md). Pour plus d’informations, consultez la section « Accélérateurs spéciales » dans cet article.  
  
## <a name="shared-memory"></a>Mémoire partagée  
 Mémoire partagée est accessible par le processeur et de l’accélérateur. L’utilisation de mémoire partagée élimine ou réduit sensiblement la surcharge de copie des données entre le processeur et de l’accélérateur. Bien que la mémoire est partagée, il ne peut pas être accessibles simultanément par le processeur et l’accélérateur et cela entraîne un comportement non défini. La propriété d’un accélérateur [supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) retourne `true` Si l’accélérateur prend en charge la mémoire partagée et le [default_cpu_access_type](../Topic/accelerator::default_cpu_access_type%20Data%20Member.md) propriété obtient la valeur par défaut [access_type](../Topic/access_type%20Enumeration.md) pour la mémoire allouée sur le `accelerator`— par exemple, `array`associées à la `accelerator`, ou `array_view` objets accédés sur le `accelerator`.  
  
 Le runtime C++ AMP choisit automatiquement la meilleure valeur par défaut `access_type` pour chaque `accelerator`, mais les caractéristiques de performances (la bande passante et la latence) de mémoire partagée peuvent être pires que ceux de la mémoire de dédié accelerator (non partagés) lors de la lecture à partir de l’UC, l’écriture à partir de l’UC, ou les deux. Si procède à la mémoire partagée, ainsi que de mémoire dédiée pour la lecture et l’écriture de l’unité centrale, le runtime par défaut est `access_type_read_write`; Sinon, le runtime sélectionne par défaut plus conservatrice `access_type`, et autorise l’application à remplacer si les modèles d’accès mémoire de ses noyaux de calcul tirer parti d’une autre `access_type`.  
  
 L’exemple de code suivant montre comment déterminer si l’accélérateur par défaut prend en charge de la mémoire partagée, puis remplace le type d’accès par défaut et crée un `accelerator_view` à partir de celui-ci.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
  accelerator acc = accelerator(accelerator::default_accelerator);  
  
  // Early out if the default accelerator doesn’t support shared memory.  
  if(!acc.supports_cpu_shared_memory)  
  {  
    std::cout << "The default accelerator does not support shared memory" << std::endl;  
    return 1;  
  }  
  
  // Override the default CPU access type.  
  acc.set_default_cpu_access_type(access_type_read_write);  
  
  // Create an accelerator_view from the default accelerator. The  
  // accelerator_view reflects the default_cpu_access_type of the  
  // accelerator it’s associated with.  
  accelerator_view acc_v = acc.default_view;  
}  
  
```  
  
 Un `accelerator_view` reflète toujours le `default_cpu_access_type` de la `accelerator` lui est associée, et il ne fournit aucune interface pour remplacer ou modifier son `access_type`.  
  
## <a name="changing-the-default-accelerator"></a>Modification de l’accélérateur par défaut  
 Vous pouvez modifier l’accélérateur par défaut en appelant le `accelerator::set_default` (méthode). Vous pouvez modifier l’accélérateur par défaut pour une seule fois par application l’exécution et vous devez le modifier avant l’exécution de code sur le GPU. Retournent tous les appels de fonction suivants pour modifier le raccourci `false`. Si vous souhaitez utiliser un accélérateur différents dans un appel à `parallel_for_each`, lisez la section « À l’aide de plusieurs accélérateurs » dans cet article. L’exemple de code suivant définit l’accélérateur par défaut par un type qui n’est pas émulée n’est pas connecté à un affichage et prend en charge la double précision.  
  
```cpp  
 
    bool pick_accelerator()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator chosen_one;  
 
    auto result = 
    std::find_if(accs.begin(), accs.end(), [] (const accelerator& acc)  
 {  
    return !acc.is_emulated&& 
    acc.supports_double_precision&& 
 !acc.has_display;  
 });

 
    if (result != accs.end())  
    chosen_one = *(result);

 
    std::wcout <<chosen_one.description <<std::endl;  
 
    bool success = accelerator::set_default(chosen_one.device_path);

    return success;  
}  
 
```  
  
## <a name="using-multiple-accelerators"></a>À l’aide de plusieurs accélérateurs  
 Il existe deux façons d’utiliser plusieurs accélérateurs dans votre application :  
  
-   Vous pouvez transmettre `accelerator_view` objets pour les appels à la [parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) méthode.  
  
-   Vous pouvez construire un `array` à l’aide de son propre `accelerator_view` objet. Le runtime C + AMP obtiendra le `accelerator_view` objet capturées `array` objet dans l’expression lambda.  
  
## <a name="special-accelerators"></a>Accélérateurs spéciaux  
 Les chemins d’accès de périphérique des trois accélérateurs spéciales sont disponibles en tant que propriétés de la `accelerator` classe :  
  
- [Accelerator::direct3d_ref, données membres](../Topic/accelerator::direct3d_ref%20Data%20Member.md): cet accélérateur monothread utilise le logiciel sur le processeur pour émuler une carte graphique générique. Il est utilisé par défaut pour le débogage, mais il n’est pas utile dans la production, car il est plus lent que les accélérateurs de matériel. En outre, il est disponible uniquement dans le SDK DirectX et le Kit de Développement Windows, et il est peu susceptible d’être installé sur les ordinateurs de vos clients. Pour plus d’informations, consultez [débogage du Code GPU](../Topic/Debugging%20GPU%20Code.md).  
  
- [Accelerator::direct3d_warp, données membres](../Topic/accelerator::direct3d_warp%20Data%20Member.md): cet accélérateur fournit une solution de secours pour l’exécution de code C++ AMP sur les processeurs multicœurs qui utilisent les Extensions Streaming SIMD (SSE).  
  
- [Accelerator::cpu_accelerator, données membres](../Topic/accelerator::cpu_accelerator%20Data%20Member.md): vous pouvez utiliser cet accélérateur pour configurer la mise en lots des tableaux. Il ne peut pas exécuter du code C++ AMP. Pour plus d’informations, consultez la [intermédiaire des tableaux en C++ AMP](http://go.microsoft.com/fwlink/p/LinkId=248485) post sur la programmation parallèle en Code natif blog.  
  
## <a name="interoperability"></a>Interopérabilité  
 Le runtime C++ AMP prend en charge l’interopérabilité entre les `accelerator_view` classe et le Direct3D [ID3D11Device interface](http://go.microsoft.com/fwlink/p/LinkId=248488). Le [create_accelerator_view](../Topic/create_accelerator_view%20Function.md) méthode prend un `IUnknown` interface et retourne un `accelerator_view` objet. Le [get_device](http://msdn.microsoft.com/fr-fr/8194125e-8396-4d62-aa8a-65831dea8439) méthode prend un `accelerator_view` objet et retourne un `IUknown` interface.  
  
## <a name="see-also"></a>Voir aussi  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Débogage du Code GPU](../Topic/Debugging%20GPU%20Code.md)   
 [accelerator_view, classe](../../parallel/amp/reference/accelerator-view-class.md)
