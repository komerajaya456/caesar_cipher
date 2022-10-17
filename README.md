# caesar_cipher
Encrypt using any KEY 
All possible keys are 26 then all will repeat sameif signed or unsigned + or -

inp=input()
alp='abcdefghijklmnopqrstuvwxyz'
def encryptwithkey(key,sentence):
	for each_char in range(0,len(sentence)):
		
		sentence=list(sentence)
		if sentence[each_char] in alp:
			loc_bef_e_c_alp=alp.find(sentence[each_char])
		
			
			loc_aft_e_c_alp=key+loc_bef_e_c_alp
		
			while loc_aft_e_c_alp>25:
				loc_aft_e_c_alp=loc_aft_e_c_alp-26
				if loc_aft_e_c_alp<=25:
					break				
					
							
			while loc_aft_e_c_alp<0:
				loc_aft_e_c_alp=loc_aft_e_c_alp+26
				if loc_aft_e_c_alp>=0: 
					break	
						
			
			
			
			sentence[each_char]=alp[loc_aft_e_c_alp]
	sentence=''.join(sentence)
	return(sentence)
lis=[]
repeated_lis=[]
for i in range(-2**50,2**50):
	each_encrypted_key=(encryptwithkey(i,inp))
	if each_encrypted_key not in lis:
		lis.append(each_encrypted_key)
	else:
		repeated_lis.append(each_encrypted_key)
print(lis)
print(repeated_lis)
