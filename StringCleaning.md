This is version v1 21 May 2014 of the roadmap for String cleaning

###candidates for removal.

* asLegalSelector
* asIdentifier:
* aPathName

	asPathName
	
		^ self.

###look at copy usage 
the way string are copied is a bit inconsistent some uses copy other new:


	asLowercase
		"Answer a String made up from the receiver whose characters are all 
		lowercase."
	
		^ self copy asString translateToLowercase
		
vs
	

	asOctetString
		"Convert the receiver into an octet string, if possible"
		"(IE, I am a WideString containing only character with codePoints < 255, so all of them fit in a latin1-string)."
		| string |
		string := String new: self size.
		1 to: self size do: [:i | string at: i put: (self at: i)].
		^string

### rename

* asSmalltalkComment -> asComment
* asUncommentedSmalltalkCode -> asUncommentedCode

* endsWith: -> isEndingWith:

* Move convertToSystemString to ZipArchive for the moment

