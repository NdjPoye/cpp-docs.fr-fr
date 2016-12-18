---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un programme&#160;console Win32 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "vcfirstapp"
  - "vccreatefirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications en ligne de commande (C++), standard"
  - "applications standard (C++)"
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un programme&#160;console Win32 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser Visual C\+\+ dans l'environnement de développement intégré \(IDE\) Visual Studio pour créer des programmes C\+\+ standard.  En suivant les étapes de cette procédure pas à pas, vous pourrez créer un projet, ajouter un nouveau fichier au projet, modifier le fichier pour ajouter du code C\+\+, puis compiler et exécuter le programme à l'aide de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Vous pouvez taper votre propre programme C\+\+ ou utiliser l'un des exemples de programmes.  L'exemple de programme de cette procédure pas à pas est une application console.  Cette application utilise le conteneur `set` de la bibliothèque de types standard.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] est conforme à la norme C\+\+ 2003, avec les exceptions majeures suivantes : recherche de nom à deux étapes, spécifications d'exception et exportation.  En outre, [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] prend en charge plusieurs fonctionnalités C\+\+0x, par exemple, lambda, auto, static\_assert, les références de rvalue et les modèles extern.  
  
> [!NOTE]
>  Si la conformité à la norme est obligatoire, utilisez l'option du compilateur **\/Za** pour désactiver les extensions Microsoft de la norme.  Pour plus d'informations, consultez [\/Za, \/Ze \(Désactiver les extensions de langage\)](../build/reference/za-ze-disable-language-extensions.md).  
  
## Composants requis  
 Pour compléter cette procédure pas à pas, vous devez comprendre les notions de base du langage C\+\+.  
  
### Pour créer un projet et ajouter un fichier source  
  
1.  Créez un projet en pointant sur **Nouveau** dans le menu **Fichier** puis en cliquant sur **Projet**.  
  
2.  Dans le volet de types projet **Visual C\+\+**, cliquez sur **Win32**, puis sur **Application console Win32**.  
  
3.  Tapez un nom pour le projet.  
  
     Par défaut, la solution qui contient le projet porte le même nom que le projet, mais vous pouvez choisir un nom différent.  Vous pouvez également taper un emplacement différent pour le projet.  
  
     Cliquez sur **OK** pour créer le projet.  
  
4.  Dans l'**Assistant Application Win32**, cliquez sur **Suivant**, sélectionnez **Projet vide**, puis cliquez sur **Terminer**.  
  
5.  Si l'**Explorateur de solutions** n'est pas visible, cliquez sur **Explorateur de solutions** dans le menu **Affichage**.  
  
6.  Ajoutez un nouveau fichier source au projet, comme suit.  
  
    1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **Fichiers sources**, pointez sur **Ajouter**, puis cliquez sur **Nouvel élément**.  
  
    2.  Dans le nœud **Code**, cliquez sur **Fichier C\+\+ \(.cpp\)**, tapez un nom pour le fichier, puis cliquez sur **Ajouter**.  
  
     Le fichier .cpp apparaît dans le dossier Fichiers sources dans l'**Explorateur de solutions** et le fichier s'ouvre dans l'éditeur Visual Studio.  
  
7.  Dans le fichier ouvert dans l'éditeur, tapez un programme C\+\+ valide qui utilise la bibliothèque C\+\+ standard ou copiez l'un des exemples de programmes et collez\-le dans le fichier.  
  
     Par exemple, vous pouvez utiliser l'exemple de programme [set::find](../misc/set-find-stl-samples.md), qui est l'un des exemples de bibliothèque de types standard inclus dans l'Aide.  
  
     Si vous utilisez l'exemple de programme, remarquez la directive `using namespace std;`.  Cette directive permet au programme d'utiliser `cout` et `endl` sans nécessiter de noms qualifiés complets \(`std::cout` et `std::endl`\).  
  
8.  Enregistrez le fichier.  
  
9. Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     La fenêtre **Sortie** affiche des informations sur la progression de la compilation, telles que l'emplacement du journal de génération et un message indiquant l'état de la build.  
  
10. Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  
  
     Si vous avez utilisé l'exemple de programme, une fenêtre de commande s'affiche et indique si certains entiers ont été trouvés dans l'ensemble.  
  
## Étapes suivantes  
 **Précédent :** [Creating Command\-Line Applications \(C\+\+\)](http://msdn.microsoft.com/fr-fr/2505d9ed-aca4-426a-9071-078a2d707254).  **Suivant :** [Procédure pas à pas : compilation d'un programme C\+\+ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)