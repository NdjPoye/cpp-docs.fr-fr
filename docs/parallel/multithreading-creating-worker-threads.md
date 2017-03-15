---
title: "Multithreading&#160;: cr&#233;ation de threads de travail | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tâches en arrière-plan (C++)"
  - "multithreading (C++), threads de travail"
  - "threads (C++), créer des threads"
  - "threads (C++), entrée d'utilisateur non requise"
  - "threads (C++), threads de travail"
  - "threads (MFC), threads de travail"
  - "threads de travail (C++)"
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Multithreading&#160;: cr&#233;ation de threads de travail
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un thread de travail est généralement utilisé pour traiter les tâches d'arrière\-plan dont l'utilisateur ne doit pas attendre la terminaison avant de continuer à utiliser votre application.  Des tâches comme le recalcul et l'impression en arrière\-plan sont de bons exemples de threads de travail.  Cette rubrique décrit en détail les étapes nécessaires à la création de threads de travail.  Les rubriques traitées ici sont les suivantes :  
  
-   [Démarrage du thread](#_core_starting_the_thread)  
  
-   [Implémentation de la fonction de contrôle](#_core_implementing_the_controlling_function)  
  
-   [Exemple](#_core_controlling_function_example)  
  
 La création d'un thread de travail est une tâche relativement simple.  Deux étapes suffisent pour lancer l'exécution du thread : l'implémentation de la fonction de contrôle et le démarrage du thread.  Il n'est pas nécessaire de dériver une classe de [CWinThread](../mfc/reference/cwinthread-class.md).  C'est possible, si vous avez besoin d'une version spéciale de `CWinThread`, mais cette opération est superflue pour la plupart des threads de travail simples.  Vous pouvez utiliser `CWinThread` sans modification.  
  
##  <a name="_core_starting_the_thread"></a> Démarrage du thread  
 Il existe deux versions surchargées d'`AfxBeginThread` : l'une qui peut seulement créer des threads de travail et l'autre qui peut créer des threads d'interface utilisateur et des threads de travail.  Pour commencer l'exécution de votre thread de travail à l'aide de la première surcharge, appelez [AfxBeginThread](../Topic/AfxBeginThread.md), en fournissant les informations suivantes :  
  
-   L'adresse de la fonction de contrôle.  
  
-   Le paramètre à passer à la fonction de contrôle.  
  
-   \(Facultatif\) La priorité du thread.  La priorité normale correspond à la valeur par défaut.  Pour plus d'informations sur les niveaux de priorité disponibles, consultez [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
-   \(Facultatif\) La taille de la pile du thread.  La valeur par défaut est la même taille de pile que celle du thread parent.  
  
-   \(Facultatif\) **CREATE\_SUSPENDED** si vous souhaitez que le thread soit créé dans un état suspendu.  La valeur par défaut est 0, ou démarrez le thread normalement.  
  
-   \(Facultatif\) Les attributs de sécurité souhaités.  La valeur par défaut est le même accès que le thread parent.  Pour plus d'informations sur le format de ces données de sécurité, consultez [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread` crée et initialise un objet `CWinThread` à votre place, le lance et retourne son adresse afin que puissiez vous y référer ultérieurement.  Des vérifications sont effectuées tout au long de la procédure pour s'assurer que tous les objets sont libérés correctement au cas où une partie de la création échouerait.  
  
##  <a name="_core_implementing_the_controlling_function"></a> Implémentation de la fonction de contrôle  
 La fonction de contrôle définit le thread.  Quand cette fonction est ouverte, le thread démarre, et quand elle est fermée, le thread s'arrête.  Cette fonction doit avoir le prototype suivant :  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 Le paramètre est une valeur simple.  La valeur que la fonction reçoit dans ce paramètre est la valeur passée au constructeur lors de la création de l'objet thread.  La fonction de contrôle peut interpréter cette valeur d'une manière quelconque.  Elle peut être traitée en tant que valeur scalaire, en tant que pointeur désignant une structure contenant plusieurs paramètres, ou elle peut être ignorée.  Si le paramètre désigne une structure, celle\-ci peut être utilisée non seulement pour passer les données de l'appelant au thread, mais également pour repasser les données du thread à l'appelant.  Si vous utilisez une telle structure pour repasser les données à l'appelant, le thread doit notifier l'appelant quand les résultats sont prêts.  Pour plus d'informations sur la communication entre le thread de travail et l'appelant, consultez [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md).  
  
 Quand la fonction s'arrête, elle doit retourner une valeur **UINT** indiquant la raison de l'arrêt d'exécution.  En principe, ce code de sortie est égal à 0 pour indiquer le succès ; d'autres valeurs sont utilisées pour indiquer différents types d'erreurs.  Ceci dépend exclusivement de l'implémentation.  Certains threads peuvent utiliser des compteurs d'utilisation des objets, et retourner le nombre de fois où cet objet a été utilisé.  Pour savoir comment les applications peuvent récupérer cette valeur, consultez [Multithreading : arrêt d'exécution des threads](../parallel/multithreading-terminating-threads.md).  
  
 Il y a des restrictions sur ce que vous pouvez faire dans un programme multithread écrit avec la bibliothèque MFC.  Pour plus d'informations sur ces restrictions et d'autres conseils concernant l'utilisation des threads, consultez [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md).  
  
##  <a name="_core_controlling_function_example"></a> Exemple de fonction de contrôle  
 L'exemple suivant montre comment définir une fonction de contrôle et l'utiliser à partir d'une autre partie du programme.  
  
```  
UINT MyThreadProc( LPVOID pParam )  
{  
    CMyObject* pObject = (CMyObject*)pParam;  
  
    if (pObject == NULL ||  
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))  
    return 1;   // if pObject is not valid  
  
    // do something with 'pObject'  
  
    return 0;   // thread completed successfully  
}  
  
// inside a different function in the program  
.  
.  
.  
pNewObject = new CMyObject;  
AfxBeginThread(MyThreadProc, pNewObject);  
.  
.  
.  
```  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Multithreading : création de threads d'interface utilisateur](../parallel/multithreading-creating-user-interface-threads.md)  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md)