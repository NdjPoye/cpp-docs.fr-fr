---
title: "threadprivate | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "threadprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threadprivate OpenMP directive"
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# threadprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

spécifie qu'une variable est privée à un thread.  
  
## Syntaxe  
  
```  
#pragma omp threadprivate(var)  
```  
  
## Notes  
 où,  
  
 `var`  
 Une liste avec la virgule comme séparateur des variables que vous souhaitez rendre exclusives à un thread.  `var` doit être une variable global\- ou de l'espace de noms\-scoped ou une variable statique locale.  
  
## Notes  
 La directive d' `threadprivate` ne prend en charge aucune clauses OpenMP.  
  
 Pour plus d'informations, consultez [directive de 2.7.1 threadprivate](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 La directive d' `threadprivate` est basée sur l'attribut de [thread](../../../cpp/thread.md)`__declspec` ; les limites sur **\_\_declspec \(thread\)** s'appliquent à `threadprivate`.  
  
 vous ne pouvez pas utiliser `threadprivate` dans aucun DLL qui sera chargé par l'intermédiaire de [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Cela inclut les DLL qui sont chargés avec [\/DELAYLOAD \(Différer le chargement de l'importation\)](../../../build/reference/delayload-delay-load-import.md), qui utilise également **LoadLibrary**.  
  
 Vous pouvez utiliser `threadprivate` dans une DLL qui est statiquement chargé au démarrage de processus.  
  
 Étant donné qu' `threadprivate` est basé sur **\_\_declspec \(thread\)**, une variable d' `threadprivate` existera dans n'importe quel thread démarré dans le processus, et pas seulement les threads qui font partie d'une équipe de thread engendrée par une région parallèle.  C'est un détail d'implémentation dont vous pouvez souhaiter connaître, puisque vous pouvez remarquer, par exemple, les constructeurs pour un type défini par l'utilisateur d' `threadprivate` appelé plus souvent ensuite prévu.  
  
 Une variable d' `threadprivate` d'un type destructable n'est pas garanti avoir son destructeur appelé.  Par exemple :  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Les utilisateurs n'ont aucun contrôle sur à lorsque les threads principaux de la région parallèle s'arrête.  Si ces threads existent lors de la sortie du processus, les threads ne seront pas notifications sur la sortie de processus, et le destructeur ne sera pas appelé pour `threaded_var` sur aucun thread sauf celui qui se ferme \(ici, le thread principal\).  Ce code ne doit pas compter sur la destruction appropriée des variables d' `threadprivate` .  
  
## Exemple  
 Pour un exemple d'utilisation `threadprivate`, consultez [privé](../../../parallel/openmp/reference/private-openmp.md).  
  
## Voir aussi  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)