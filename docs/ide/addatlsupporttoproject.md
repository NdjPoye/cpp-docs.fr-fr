---
title: "AddATLSupportToProject | Microsoft Docs"
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
  - "AddATLSupportToProject (méthode)"
ms.assetid: 26708f22-1e9b-4432-83b2-ed94c765b753
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AddATLSupportToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute la prise en charge ATL à un projet MFC.  
  
## Syntaxe  
  
```  
  
      function AddATLSupportToProject(   
   oProj   
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
## Valeur de retour  
 Retourne **true** si la prise en charge ATL a été ajoutée correctement au projet MFC.  
  
## Notes  
 Utilisez cette fonction pour ajouter la prise en charge ATL à un projet MFC créé par l'Assistant.  
  
 L'Assistant affiche une boîte de message pour confirmer l'ajout de la prise en charge ATL au projet MFC.  L'Assistant vérifie ensuite que la prise en charge a réussi et ajoute tous les GUID, modèles, en\-têtes et autres fonctionnalités nécessaires pour assurer la prise en charge ATL dans le projet MFC.  
  
## Exemple  
  
```  
var oCM = selProj.CodeModel;  
var L_TRANSACTION_Text = "Add ATL Support To Project";  
oCM.StartTransaction(L_TRANSACTION_Text);  
var bRet = AddATLSupportToProject(selProj);  
if (bRet)  
   oCM.CommitTransaction();  
else  
   oCM.AbortTransaction();  
return bRet;  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)   
 [Introduction to ATL](../atl/introduction-to-atl.md)