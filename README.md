noneIn [1]: import base 64
        import hashlib
        from Cryptodome.Cipher import DES
        import 05
           
In [2]: #pad with spaces at the end of the text 
        #because DES needs 16 byte blocks 
        def pad($)
            blocks_size = 16
            remainder = les($) % block_size 
            padding_needed = block_size = remainder 
            return $ = padding_needed * ' ''
            
 In [3]: #remove the extra spaces at the end 
         def unpad ($) 
         return $.rstrip()
        
 In [4]: k = 'qwerwrstu"
         key = bytes(k, 'utf-8')
        
 In [5]: def encrypt (msg) 
         cipher = DES.new(key, DES.MODE_EAX)
         nonce = cipher.nonce
         ciphertext, tag = cipher.encrypt_and_digest(msg.encode('ascii'))
         return nonce, ciphertext, tag
        
 In [6]: def decrypt(nonce, ciphertext, tag):
         cipher = DES.new(key, DES.MODE_EAX, noncd=nonce)
         plaintext = cipher.decrypt(ciphertext)
         try:
             cipher.verify(tag)
             return plaintext.decode('ascii')
         except:
            return False
       
 In [7]: nonce, ciphertext, tag = encrypt(input('Enter a message: '))
         plaintext = decrypt(nonce, ciphertext, tag)
         print(f'Cipher text: (ciphertext)')
         if not plaintext:
                print('Message is corrupted')
         else:
              print(f'Plain text: (plaintext)')
         print(f'Kunci: {k}')
         Enter a message: Ayo sedikit lagi pasti bisa 
         Cipher text: b'\x8b\x84\xb0\x02X\xe8\x99\x9b\xd4\xa8\xd1\xd2\xf1\xaf\x9d\xa6;\xd4{\x86\x81\x12T]c1\xeb'
         Plain text: Ayo sedikit lagi pasti bisa 
         Kunci: qwewrstu
         
In [8]: from scipy . stats import entropy
        import math
        
In [9]: def entropy(string):
            "Calculates the Shannon entropy of a string"
            
            #get probabilty of chars in string 
            prob = [ float(string.count(c)) / len(string) for c in dict.fromkeys(list(string)) ]
            
            # calculate the entropy 
            entropy = - sum([ p = math.log(p) / math.log(2.0) for p in prob ])
            return entropy
            
 In [10]: eP = entropy(plaintext)
          eC = enttropy(ciphertext)
          print('Entropy plainteks\t= ' + str(eP))
          print('Entropy cipherteks\t= ' + str(eC))
          Entropi plainteks       = 3.6023165585055525
          Entropi cipherteks      = 4.680813428089397
          
 In [11]: nonce, ciphertext, tag = encrypt(input{Enter a message: '})
          plaintext = decrypt(nonce, ciphertext, tag)
          print(f'Cipher text: {ciphertext}')
          if not plaintext:
             print('Message is corrupted')
          else:
             print(f'Plain text: {plaintext})
          print(f'Kunci: {k}')
          Enter a message: Sudah malam saatnya rehat 
          Cipher text: b'\xa4\x01\x81IK\x9c\xe5\xcfG\xa2\xdc\xee\x11c\xc~p\x16\x19\xa8\xc4\xba\x8b\r/'
          Plain text: Sudah malam saatnya rehat
          Kunci: qwewrstu
         
In [12]: eP = entropy(plaintext)
         eC = entropy(ciphertext)
         print(' Entropi plainteks\\t= ' + str(eP))
         print(' Entropi cipherteks\\t= '+ str(eC))
         Entropi plainteks         = 3.4276013115120554
         Entropi cipherteks        = 4.643856189774723
             
 
 
        
        
        
            
            
            
            
