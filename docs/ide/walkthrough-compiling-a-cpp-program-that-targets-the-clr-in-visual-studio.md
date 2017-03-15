---
title: "Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++ qui cible le CLR dans Visual Studio | Microsoft Docs"
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
helpviewer_keywords: 
  - "applications en ligne de commande (C++), code managé"
  - "compiler des programmes (C++)"
  - "code managé (C++)"
  - "Visual C++, code managé"
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++ qui cible le CLR dans Visual Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer des programmes Visual C\+\+ qui utilisent des classes .NET et les compiler à l'aide de l'environnement de développement Visual Studio.  
  
 Pour cette procédure, vous pouvez taper votre propre programme Visual C\+\+ ou utiliser l'un des exemples de programme.  L'exemple de programme que nous utilisons dans cette procédure crée un fichier texte nommé textfile.txt et l'enregistre dans le répertoire du projet.  
  
## Composants requis  
 Ces rubriques supposent que vous comprenez les notions de base du langage C\+\+.  
  
### Pour créer un nouveau projet dans Visual Studio et ajouter un nouveau fichier source  
  
1.  Créer un nouveau projet.  Dans le menu **Fichier**, pointez sur **Nouveau**, puis cliquez sur **Projet...**.  
  
2.  Dans les types de projets Visual C\+\+, cliquez sur **CLR**, puis sur **Projet vide CLR**.  
  
3.  Tapez un nom de projet.  
  
     Par défaut, la solution qui contient le projet porte le même nom que le nouveau projet, mais vous pouvez saisir un nom différent.  Vous pouvez définir un emplacement différent pour le projet si vous le souhaitez.  
  
     Cliquez sur **OK** pour créer le nouveau projet.  
  
4.  Si l'Explorateur de solutions n'est pas visible, cliquez sur **Explorateur de solutions** dans le menu **Affichage**.  
  
5.  Pour ajouter un fichier source au projet :  
  
    -   Cliquez avec le bouton droit sur le dossier **Fichiers sources** dans l'Explorateur de solutions, pointez sur **Ajouter** et cliquez sur **Nouvel élément**.  
  
    -   Cliquez sur **Fichier C\+\+ \(.cpp\)** et tapez un nom de fichier, puis cliquez sur **Ajouter**.  
  
     Le fichier **.cpp** apparaît dans le dossier **Fichiers sources** dans l'Explorateur de solutions et une fenêtre avec des onglets apparaît, dans laquelle vous saisissez le code que vous voulez voir figurer dans ce fichier.  
  
6.  Cliquez dans l'onglet nouvellement créé dans Visual Studio, puis saisissez un programme Visual C\+\+ valide, ou copiez et collez l'un des exemples de programmes.  
  
     Par exemple, vous pouvez utiliser l'exemple de programme [Comment : écrire un fichier texte](../dotnet/how-to-write-a-text-file-cpp-cli.md) \(dans le nœud **Gestion et E\/S de fichiers** du Guide de programmation\).  
  
     Si vous utilisez l'exemple de programme, notez que vous utilisez le mot clé `gcnew` ``  au lieu de `new` lors de la création d'un objet .NET et que `gcnew` retourne un handle \( `^`\) au lieu d'un pointeur \(`*`\) :  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Pour plus d'informations sur cette nouvelle syntaxe Visual C\+\+, consultez [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     La fenêtre **Sortie** affiche des informations sur la progression de la compilation, telles que l'emplacement du journal de génération et un message indiquant l'état de la build.  
  
     Si vous apportez des modifications et exécutez le programme sans effectuer une génération, une boîte de dialogue peut indiquer que le projet est obsolète.  Activez la case à cocher dans cette boîte de dialogue avant de cliquer sur **OK** si vous souhaitez que Visual Studio utilise toujours les versions actuelles des fichiers au lieu de vous inviter chaque fois qu'il génère l'application.  
  
8.  Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  
  
9. Si vous avez utilisé l'exemple de programme, une fenêtre de commande s'affiche à l'exécution du programme, indiquant que le fichier texte a été créé.  Appuyez sur n'importe quelle touche pour fermer la fenêtre de commande.  
  
     Le fichier texte **textfile.txt** se trouve à présent dans le répertoire de votre projet.  Vous pouvez ouvrir ce fichier en utilisant le Bloc\-notes.  
  
    > [!NOTE]
    >  Le choix du modèle de projet vide CLR définit automatiquement l'option **\/clr** du compilateur.  Pour ce faire, cliquez avec le bouton droit sur le projet dans l'**Explorateur de solutions** et cliquez sur **Propriétés**, puis vérifiez l'option **Prise en charge du Common Language Runtime** dans le nœud **Général** des **Propriétés de configuration**.  
  
## Quoi d'autre ?  
 **Précédent :** [Procédure pas à pas : compilation d'un programme C\+\+ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **Suivant :** [Procédure pas à pas : compilation d'un programme C sur la ligne de commande](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)