---
title: "Gestion des erreurs dans des fichiers JScript d&#39;Assistant | Microsoft Docs"
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
  - "gestion des erreurs, JScript"
  - "JScript, gérer les erreurs"
  - "gérer les erreurs JScript dans les Assistants"
ms.assetid: 6df3ba46-7ab6-484c-ac45-b08f4b6a5900
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des erreurs dans des fichiers JScript d&#39;Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous créez un Assistant, votre projet inclut les fichiers Default.js et Common.js.  Utilisez ces fichiers pour personnaliser votre projet.  Consultez [Le fichier Jscript](../ide/jscript-file.md) pour plus d'informations.  
  
 Votre projet doit inclure une gestion des erreurs.  Le code ci\-dessous fournit un exemple d'un tel code.  
  
### Pour gérer les erreurs en JScript  
  
1.  Pour intercepter les erreurs quand l'utilisateur clique sur **Terminer**, entrez le code suivant :  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       try  
       {  
          .....  
       }  
       catch(e)  
       {  
          if (e.description.length != 0)  
             SetErrorInfo(e.description, e.number);  
          return e.number  
       }  
    }  
    ```  
  
2.  Levez `e` à partir de toutes les fonctions d'assistance de script appelées dans le script :  
  
    ```  
    function ExtenderFromType(strVariableType)  
    {  
       try  
       {  
          ....  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
3.  Si le paramètre **PREPROCESS\_FUNCTION** est dans [le fichier .vsz](../ide/dot-vsz-file-project-control.md), l'Assistant appelle [CanAddATLClass](../ide/jscript-functions-for-cpp-wizards.md).  En cas d'échec, utilisez [SetErrorInfo](../ide/seterrorinfo.md) pour retourner **false** :  
  
    ```  
    function CanAddATLClass(oProj, oObject)  
    {  
       try  
       {  
          if (!IsATLProject(oProj))  
          {  
             if (!IsMFCProject(oProj, true))  
             {     
                var L_CanAddATLClass_Text = "ATL classes can only be added  
     to ATL, MFC EXE and MFC regular DLL projects.";  
                wizard.ReportError(L_CanAddATLClass_Text);  
                return false;  
             }  
             else  
             {  
                .....  
                var bRet = AddATLSupportToProject(oProj);  
                .....  
                return bRet;  
             }  
          }  
          return true;  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
4.  Si vous devez revenir à la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément**, retourne **VS\_E\_WIZBACKBUTTONPRESS** :  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       ....  
       if (!CheckAddtoProject(selProj))  
       {  
          return VS_E_WIZARDBACKBUTTONPRESS;  
       }  
    }  
    ```  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Personnalisation de votre Assistant](../ide/customizing-your-wizard.md)