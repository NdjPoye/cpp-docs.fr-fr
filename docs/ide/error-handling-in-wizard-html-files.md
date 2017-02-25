---
title: "Gestion des erreurs dans les fichiers HTML d&#39;Assistant | Microsoft Docs"
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
  - "gestion des erreurs, vérification des erreurs de fichiers"
  - "HTML, gestion des erreurs"
ms.assetid: eb428a64-b681-4420-987d-92098bf98455
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gestion des erreurs dans les fichiers HTML d&#39;Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous créez un Assistant avec une interface utilisateur, votre projet inclut les fichiers .htm.  Utilisez ces fichiers pour personnaliser votre projet.  Pour plus d'informations, consultez [Les fichiers HTML](../ide/html-files.md).  
  
 Votre projet doit inclure une gestion des erreurs.  Le code ci\-dessous fournit un exemple d'un tel code.  
  
### Pour gérer les erreurs en HTML  
  
1.  Lors de la validation des champs, si vous appelez une méthode de validation dans une DLL \(qui doit définir l'information sur l'erreur\), appelez `ReportError` sans paramètre.  
  
    ```  
    function ValidateInput()  
    {  
       if (!window.external.ValidateFile(HEADER_FILE.value))  
       {  
          ReportError();  
          HEADER_FILE.focus();  
          return false;  
       }  
    }  
    ```  
  
2.  Lors de la validation des champs, si vous validez le champ seulement à partir du script HTML, appelez `SetErrorInfo` d'abord, puis `ReportError` sans paramètre.  
  
    ```  
    function OnWhatever()  
    {  
       if (!ValidateInput())  
          window.external.ReportErrror();  
       ....  
    }  
  
    function ValidateInput()  
    {  
       .....  
  
       if (HEADER_FILE.value == IMPL_FILE.value)  
       {  
          var L_ErrMsg_Text = "Header and implementation files cannot have the same name.";  
          SetErrorInfo(L_ErrMsg_Text);  
          bValid = false;  
       }  
       if (TYPE.value == "")  
       {  
          var L_ErrMsg4_Text = "Type cannot be blank.";  
          SetErrorInfo(L_ErrMsg4_Text);  
          bValid = false;  
       }  
       return bValid;  
    }  
    ```  
  
3.  Appelez `ReportError` avec des paramètres :  
  
    ```  
    function ValidateInput()  
    {  
       if (!IsListed(strType))  
       {  
          var L_Invalid2_Text = "The variable type should be one of the types listed.";  
          window.external.ReportError(L_Invalid2_Text);  
          VariableType.focus();  
          return false;  
       }  
    }  
    ```  
  
4.  Si vous devez revenir à la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément**, retourne **VS\_E\_WIZBACKBUTTONPRESS** :  
  
    ```  
    try  
    {  
       oCM   = window.external.ProjectObject.CodeModel;  
    }  
    catch(e)  
    {  
       var L_NCBError_Text = "Cannot access the Class View information   
    file. Class View information will not be available.";  
       window.external.ReportError(L_NCBError_Text);  
       return VS_E_WIZARDBACKBUTTONPRESS;  
    ```  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Personnalisation de votre Assistant](../ide/customizing-your-wizard.md)