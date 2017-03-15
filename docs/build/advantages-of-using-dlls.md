---
title: "Avantages de l&#39;utilisation des DLL | Microsoft Docs"
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
  - "DLL (C++), avantages"
  - "liaison dynamique (C++)"
  - "liaison de charge dynamique (C++)"
  - "liaison (C++), comparaison entre dynamique et statique"
  - "liens (C++), comparaison entre dynamique et statique"
ms.assetid: 8956c8ee-e7b3-446f-a0c6-462381747690
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avantages de l&#39;utilisation des DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La liaison dynamique offre les avantages suivants :  
  
-   Économise la mémoire et réduit l'échange.  De nombreux processus peuvent utiliser simultanément une seule DLL, partageant ainsi une même copie de la DLL en mémoire.  En revanche, Windows doit charger en mémoire une copie du code de la bibliothèque pour chaque application générée à l'aide d'une bibliothèque de liaison statique.  
  
-   Économise l'espace disque.  De nombreuses applications peuvent partager une même copie de la DLL sur le disque.  Par contre, chaque application générée à l'aide de la bibliothèque de liaison statique a le code de la bibliothèque lié dans l'image de son exécutable en tant que copie séparée.  
  
-   Simplifie les mises à niveau de la DLL.  Lorsque les fonctions d'une DLL changent, les applications qui les utilisent n'ont pas besoin d'être recompilées ni rééditées du moment que les arguments et les valeurs de retour des fonctions ne sont pas modifiés.  En revanche, le code objet lié de manière statique exige que les liens de l'application soient réédités quand les fonctions changent.  
  
-   Permet d'assurer un support pour les produits « après marché ».  Par exemple, la DLL d'un pilote d'écran peut être modifiée pour prendre en charge un écran qui n'était pas disponible au moment de la commercialisation de l'application.  
  
-   Prend en charge les programmes multilangages.  Les programmes écrits dans différents langages de programmation peuvent appeler la même fonction de la DLL du moment qu'ils respectent la convention d'appel de la fonction.  Les programmes et la fonction de la DLL doivent être compatibles sur les plans suivants : l'ordre dans lequel la fonction s'attend à ce que ses arguments soient l'objet d'un push sur la pile, la fonction ou l'application responsable du nettoyage de la pile et les arguments éventuellement passés aux registres.  
  
-   Met en œuvre un mécanisme d'extension des classes de la bibliothèque MFC.  Vous pouvez dériver des classes à partir de classes MFC existantes et les placer dans une DLL d'extension MFC en vue de leur utilisation par des applications MFC.  
  
-   Facilite la création de versions internationales.  En plaçant des ressources dans une DLL, il est beaucoup plus aisé de créer des versions internationales d'une application.  Vous pouvez placer les chaînes de chaque version linguistique de votre application dans une DLL de ressource séparée et laisser les différentes versions linguistiques charger ensuite les ressources appropriées.  
  
 Les DLL présentent néanmoins un inconvénient potentiel : l'application n'est pas autonome ; elle a besoin d'un module de DLL séparé.  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
-   [Lier un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DLL non\-MFC : vue d'ensemble](../build/non-mfc-dlls-overview.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension : vue d'ensemble](../build/extension-dlls-overview.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)