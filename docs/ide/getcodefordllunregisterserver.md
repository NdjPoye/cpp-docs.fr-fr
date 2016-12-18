---
title: "GetCodeForDllUnregisterServer | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllUnregisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllUnregisterServer (méthode)"
ms.assetid: 6b152943-8c30-49f4-a55c-d0cba8d27a17
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllUnregisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le code nécessaire pour annuler l’inscription d’un serveur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      function GetCodeForDllUnregisterServer(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nLineStart`  
 Numéro de ligne de base zéro du début de la fonction.  
  
 `nLineEnd`  
 Numéro de ligne de base zéro de la fin de la fonction.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaîne contenant le code de votre désinscription du serveur.  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction membre pour récupérer le code nécessaire pour annuler l’inscription du serveur :  
  
|Numéro de ligne|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) ;|  
|1|_AtlModule.UpdateRegistryAppId(false) ;|  
|2|HRESULT hRes = _AtlModule.UnregisterServer(TRUE) ;|  
|3|Si (hRes ! = S_OK)|  
|4|hRes \treturn ;|  
|5|if ( !. COleObjectFactory::UpdateRegistryAll(FALSE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS) ;|  
|7|Retourne S_OK ;|  
  
 Pour chacune des lignes retournées, `GetCodeForDllUnregisterServer` ajoute une tabulation à gauche (`\t`) et une paire de caractères « CR-LF » (retour chariot - saut de ligne) à droite (`\r\n`).  
  
## <a name="example"></a>Exemple  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllUnregisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.UnregisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des Assistants C++ à l’aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d’un Assistant](../ide/designing-a-wizard.md)   
 [GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)