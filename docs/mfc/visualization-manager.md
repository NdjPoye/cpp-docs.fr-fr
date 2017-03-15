---
title: "Gestionnaire de visualisation | Microsoft Docs"
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
  - "gestionnaire de visualisation"
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gestionnaire de visualisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le gestionnaire visuel est un objet qui contrôle l'apparence d'une application complète.  Il agit comme une seule classe dans laquelle vous pouvez mettre le code de dessin pour votre application.  La bibliothèque MFC inclut plusieurs gestionnaires visuels.  Vous pouvez également créer votre propre gestionnaire visuel si vous souhaitez créer une vue personnalisée pour votre application.  Les illustrations suivantes montrent la même application lorsque différents gestionnaires visuels sont activés :  
  
 ![MyApp rendu par CMFCVisualManagerWindows](../mfc/media/vmwindows.png "VMWindows")  
MyApp qui utilise le gestionnaire de visuel de CMFCVisualManagerWindows  
  
 ![MyApp rendu par CMFCVisualManagerVS2005](../mfc/media/vmvs2005.png "VMVS2005")  
MyApp qui utilise le gestionnaire de visuel de CMFCVisualManagerVS2005  
  
 ![MyApp rendu par CMFCVisualManagerOfficeXP](../mfc/media/vmofficexp.png "VMOfficeXP")  
MyApp qui utilise le gestionnaire de visuel de CMFCVisualManagerOfficeXP  
  
 ![MyApp rendu par CMFCVisualManagerOffice2003](../mfc/media/vmoffice2003.png "VMOffice2003")  
MyApp qui utilise le gestionnaire de visuel de CMFCVisualManagerOffice2003  
  
 ![MyApp rendu par CMFCVisualManagerOffice2007](../mfc/media/msoffice2007.png "MSOffice2007")  
MyApp qui utilise le gestionnaire de visuel de CMFCVisualManagerOffice2007  
  
 Par défaut, le gestionnaire visuel contient le code de dessin de plusieurs éléments d'interface utilisateur graphique.  Pour fournir des éléments personnalisés de l'interface utilisateur, vous devez redéfinir les méthodes associées de dessin du gestionnaire visuel.  Pour obtenir la liste de ces méthodes, consultez [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md).  Les méthodes que vous pouvez remplacer pour fournir une apparence personnalisées sont toutes les méthodes qui commencent par `OnDraw`.  
  
 Votre application ne peut avoir qu'un seul objet `CMFCVisualManager`.  Pour obtenir un pointeur vers le gestionnaire visuel de votre application, appelez la fonction statique [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md).  Puisque tous les gestionnaires visuels héritent de `CMFCVisualManager`, la méthode de `CMFCVisualManager::GetInstance` obtient un pointeur vers le gestionnaire visuel approprié, même si vous créez un gestionnaire visuel personnalisé.  
  
 Si vous voulez créer un gestionnaire visuel personnalisé, vous devez la dériver d'un gestionnaire visuel qui existe déjà.  La classe par défaut dont il faut dériver est `CMFCVisualManager`.  Toutefois, vous pouvez utiliser un gestionnaire visuel différent si elle ressemble plus à ce que vous souhaitez dans votre application.  Par exemple, si vous souhaitez utiliser le gestionnaire de visuel `CMFCVisualManagerOffice2007`, mais souhaitez uniquement modifier les séparateurs, vous pourriez dériver votre classe personnalisée de `CMFCVisualManagerOffice2007`.  Dans ce scénario, vous devez remplacer uniquement les méthodes qui dessinent les séparateurs.  
  
 Il existe deux moyens possibles d'utiliser un gestionnaire visuel spécifique pour votre application.  Une méthode consiste à appeler la méthode [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md) et passer le gestionnaire visuel approprié comme paramètre.  L'exemple de code suivant montre comment utiliser `CMFCVisualManagerVS2005` avec cette méthode :  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));  
```  
  
 L'autre méthode qui permet d'utiliser un gestionnaire visuel de votre application est de le créer manuellement.  L'application utilisera alors le nouveau gestionnaire visuel pour le rendu.  Toutefois, comme il ne peut y avoir qu'un objet `CMFCVisualManager` par application, vous devez supprimer le gestionnaire visuel actuel avant d'en créer un nouveau.  Dans l'exemple suivant, `CMyVisualManager` est un gestionnaire visuel personnalisé dérivé de `CMFCVisualManager`.  La méthode suivante modifie le gestionnaire visuel utilisé pour afficher votre application, selon un index :  
  
```  
void CMyApp::SetSkin (int index)  
{  
   if (CMFCVisualManager::GetInstance() != NULL)  
   {  
      delete CMFCVisualManager::GetInstance();  
   }  
  
   switch (index)  
   {  
   case DEFAULT_STYLE:  
      // The following statement creates a new CMFCVisualManager  
      CMFCVisualManager::GetInstance();  
      break;  
  
   case CUSTOM_STYLE:  
      new CMyVisualManager;  
      break;  
  
   default:  
      CMFCVisualManager::GetInstance();  
      break;  
   }  
  
   CMFCVisualManager::GetInstance()->RedrawAll();  
}  
```  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md)