---
title: "Interception des erreurs | Microsoft Docs"
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
  - "contrôles ActiveX (C++), recouvrement des erreurs"
  - "interception des erreurs (C++)"
ms.assetid: c509b089-a542-44be-8f22-dc5832967a48
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interception des erreurs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans la liaison de données, l'interception des erreurs émane de deux sources : les événements d'erreur ou les objets d'erreur.  
  
##  <a name="vcreferrortrappingviaerrorevents"></a> L'interception des erreurs par les événements d'erreur  
 Le contrôle de données ADO et le contrôle RemoteData RDO possèdent tous deux des événements d'erreur.  En principe, vous définissez un gestionnaire d'événements d'erreur.  Les gestionnaires d'événements ont la signature suivante.  
  
```  
void CMyDlg::OnErrorAdodc1(long ErrorNumber,  
                           BSTR* FAR Description,  
                           long Scode,  
                           LPCTSTR Source,  
                           LPCTSTR HelpFile,  
                           long HelpContext,  
                           BOOL FAR* fCancelDisplay)  
```  
  
 Le champ Description est généralement renseigné, mais les champs ErrorNumber et Scode sont uniquement renseignés en cas d'erreurs COM.  Un gestionnaire d'événements standard doit afficher le champ Description dans une boîte de message.  Par exemple :  
  
```  
{  
   USES_CONVERSION;     
// note: have to include the ATL file ATLConv.h to use the ATL conversion macros  
   ::AfxMessageBox(OLE2T(*Description), MB_OK);  
}  
```  
  
 Cependant, le contrôle de données ADO et le contrôle RemoteData RDO sont déjà définis pour intercepter des événements d'erreur et aucun code n'est donc nécessaire.  
  
##  <a name="vcreferrortrappingviaerrorobjects"></a> Interception des erreurs par les objets d'erreur  
 Les technologies ADO et RDO possèdent toutes deux des objets d'erreur.  Lors de la génération de [Classes wrapper](../../data/ado-rdo/wrapper-classes.md), le contrôle RemoteData RDO génère des wrappers pour les objets d'erreur, contrairement au contrôle de données ADO.  
  
 Le contrôle de données ADO affiche automatiquement des messages d'erreur ADO.  
  
## Voir aussi  
 [Liaison de données avec des contrôles ActiveX dans Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)