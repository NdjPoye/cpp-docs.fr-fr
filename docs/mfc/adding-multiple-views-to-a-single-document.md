---
title: "Ajout de plusieurs vues &#224; un seul document | Microsoft Docs"
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
  - "documents, vues multiples"
  - "vues multiples, applications SDI"
  - "interface monodocument, ajouter des vues"
  - "vues, applications SDI"
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Ajout de plusieurs vues &#224; un seul document
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une application \(SDI\) de l'interface monodocument créée avec la bibliothèque Microsoft Foundation Class \(MFC\), chaque type de document est associé avec un seul type de vue.  Dans certains cas, il est souhaitable d'avoir la possibilité de basculer de la vue actuelle d'un document à une nouvelle vue.  
  
> [!TIP]
>  Pour des procédures supplémentaires sur l'implémentation de plusieurs vues d'un seul document, consultez [CDocument::AddView](../Topic/CDocument::AddView.md) et l'exemple de [RECUEILLEZ](../top/visual-cpp-samples.md) MFC.  
  
 Vous pouvez implémenter cette fonctionnalité en ajoutant à une application existante de MFC une nouvelle classe dérivée de `CView` et du code supplémentaire pour basculer entre les vues dynamiquement.  
  
 Les étapes sont les suivantes :  
  
-   [Modifiez la classe d'application existante](#vcconmodifyexistingapplicationa1)  
  
-   [Créez et modifiez la nouvelle classe d'affichage](#vcconnewviewclassa2)  
  
-   [Créez et attachez la nouvelle vue](#vcconattachnewviewa3)  
  
-   [Implémentez la fonction de basculement](#vcconswitchingfunctiona4)  
  
-   [Ajouter la prise en charge de basculement de vue](#vcconswitchingtheviewa5)  
  
 Le reste de cette rubrique suppose les éléments suivants :  
  
-   Le nom de l'objet dérivé de `CWinApp` est `CMyWinApp`, et `CMyWinApp` est déclaré et défini dans MYWINAPP.H et MYWINAPP.CPP.  
  
-   `CNewView` est le nom du nouvel objet dérivé de `CView`, et `CNewView` est déclaré et défini dans NEWVIEW.H et NEWVIEW.CPP.  
  
##  <a name="vcconmodifyexistingapplicationa1"></a> Modifiez la classe d'application existante  
 Pour l'application de basculer entre les modes, vous devez modifier la classe d'application en ajoutant des attributs pour stocker les vues et une méthode à utiliser.  
  
 Ajoutez le code suivant à la déclaration de  `CMyWinApp` dans MYWINAPP.H :  
  
 [!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/CPP/adding-multiple-views-to-a-single-document_1.h)]  
  
 Les attributs, `m_pOldView` et `m_pNewView`, pointent sur la vue actuelle et celle nouvellement créée.  La nouvelle méthode \(`SwitchView`\) bascule les vues lorsque l'utilisateur le demande.  Le corps de la méthode est présenté plus loin dans cette rubrique dans [Implémentez la fonction de basculement](#vcconswitchingfunctiona4).  
  
 La dernière modification de la classe d'application requiert d'inclure un fichier d'en\-tête qui définit un message windows \(**WM\_INITIALUPDATE**\) utilisé dans la fonction de basculement.  
  
 Insérez la ligne suivante dans la section d'inclusion de MYWINAPP.CPP :  
  
 [!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/CPP/adding-multiple-views-to-a-single-document_2.cpp)]  
  
 Enregistrez vos modifications et passez à l'étape suivante.  
  
##  <a name="vcconnewviewclassa2"></a> Créez et modifiez la nouvelle classe d'affichage  
 Créer la nouvelle classe d'affichage est rendu simple à l'aide de la **Nouvelle classe** disponible dans l'Affichage de classes.  Le seul impératif pour cette classe est qu'elle provienne de `CView`.  Ajouter cette nouvelle classe à l'application.  Pour des informations spécifiques sur l'ajout d'une nouvelle classe au projet, consultez [Ajouter une classe](../ide/adding-a-class-visual-cpp.md).  
  
 Une fois que vous avez ajouté la classe au projet, vous devez modifier l'accessibilité des membres de la classe d'affichage.  
  
 Modifiez NEWVIEW.H en modifiant le spécificateur d'accès de `protected` à **public** pour le constructeur et le destructeur.  Cela permet à la classe d'être créée et détruite dynamiquement et de modifier l'apparence de la vue avant qu'elle soit visible.  
  
 Enregistrez vos modifications et passez à l'étape suivante.  
  
##  <a name="vcconattachnewviewa3"></a> Créez et attachez la nouvelle vue  
 Pour créer et attacher la nouvelle vue, vous devez modifier la fonction `InitInstance` de la classe d'application.  La modification ajoute un nouveau code qui crée un nouvel objet de vue puis initialise `m_pOldView` et `m_pNewView` avec les deux objets de vue existants.  
  
 Étant donné que la nouvelle vue est créée dans la fonction `InitInstance`, les vues nouvelles aussi bien qu'existantes persistent pour la durée de vie de l'application.  Toutefois, elle peut tout aussi facilement créer la nouvelle vue de façon dynamique.  
  
 Insérez le code après l'appel à `ProcessShellCommand`:  
  
 [!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/CPP/adding-multiple-views-to-a-single-document_3.cpp)]  
  
 Enregistrez vos modifications et passez à l'étape suivante.  
  
##  <a name="vcconswitchingfunctiona4"></a> Implémentez la fonction de basculement  
 Dans l'étape précédente, vous avez ajouté le code qui a créé et initialisé un nouvel objet de vue.  La dernière partie principale est d'appliquer la méthode de basculement, `SwitchView`.  
  
 À la fin du fichier d'implémentation de votre classe d'application \(MYWINAPP.CPP\), ajoutez la définition de méthode suivante :  
  
 [!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/CPP/adding-multiple-views-to-a-single-document_4.cpp)]  
  
 Enregistrez vos modifications et passez à l'étape suivante.  
  
##  <a name="vcconswitchingtheviewa5"></a> Ajouter la prise en charge de basculement de vue  
 L'étape finale implique d'ajouter le code qui appelle la méthode `SwitchView` lorsque l'application doit basculer entre les vues.  Cela peut être accompli de plusieurs manières : soit en ajoutant un nouvel élément de menu pour que l'utilisateur le choisisse soit en activant les vues en interne lorsque certaines conditions sont remplies.  
  
 Pour plus d'informations sur l'ajout de nouveaux éléments de menu et de fonctions du gestionnaire de commandes, consultez [Gestionnaires des commandes et des notifications de contrôle](../mfc/handlers-for-commands-and-control-notifications.md).  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)