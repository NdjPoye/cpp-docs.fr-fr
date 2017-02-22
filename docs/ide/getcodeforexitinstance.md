---
title: "GetCodeForExitInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForExitInstance (méthode)"
ms.assetid: 41fe3d79-a1f4-4bb5-b3f5-7859e255b4e7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForExitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le [ExitInstance](../Topic/CWinApp::ExitInstance.md) code de fin de l’Assistant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      function GetCodeForExitInstance(   
   nLineStart,   
   nLineEnd    
)   
```  
  
#### <a name="parameters"></a>Paramètres  
 `nLineStart`  
 Numéro de ligne de base zéro du début de la fonction.  
  
 `nLineEnd`  
 Numéro de ligne de base zéro de la fin de la fonction.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaîne contenant le code de sortie de l’instance de l’Assistant.  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction membre pour récupérer le code nécessaire pour quitter une instance de l’Assistant :  
  
|Numéro de ligne|Code de ExitInstance|  
|-----------------|-----------------------|  
|0|_AtlModule.RevokeClassObjects() ;|  
|1|retourner CWinApp::ExitInstance() ;|  
  
 Pour chacune des lignes retournées, `GetCodeForExitInstance` ajoute une tabulation à gauche (`\t`) et une paire de caractères « CR-LF » (retour chariot - saut de ligne) à droite (`\r\n`).  
  
## <a name="example"></a>Exemple  
  
```  
if (!oExitInstance)  
   {  
      oExitInstance = oCWinApp.AddFunction("ExitInstance",   
      vsCMFunctionFunction, "BOOL", vsCMAddPositionEnd, vsCMAccessPublic,   
      strProjectCPP);  
      oExitInstance.BodyText = GetCodeForExitInstance(0, 1);  
   }  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
// \treturn CWinApp::ExitInstance();\r\n"  
else  
   {  
   oExitInstance.StartPointOf(vsCMPartBody,   
   vsCMWhereDefinition).CreateEditPoint().Insert(GetCodeForExitInstance(0,   
   0));  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
      oCM.Synchronize();  
   }  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des Assistants C++ à l’aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d’un Assistant](../ide/designing-a-wizard.md)   
 [GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)   
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md)