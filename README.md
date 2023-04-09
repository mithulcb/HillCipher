# HillCipher
An implementaion of the hill cipher encrytpion.



The Hill cipher algorithm is one of the symmetric key algorithms that have several advantages in data encryption. While Hill ciphers provide a significant improvement in security over Vigen`ere ciphers, they are very easily attacked if a few correct characters of plaintext are already matched to a ciphertext message, a so-called known plaintext attack. For this reason, Hill ciphers are not considered sufficiently secure for sensitive applications.
<br>
A main drawback of this algorithm is that it encrypts identical plaintext blocks to identical ciphertext blocks and cannot encrypt images that contain large areas of a single color. Thus, it does not hide all features of the image which reveals patterns in the plaintext. 
However it is still highly used for its simplicity because of using matrix multiplication and inversion for encryption and decryption, and due to this simplicity, it results in high speed and high throughput
<br>

# WORKING
# 1.Encryption – Plain text to Cipher text-
Encryption is converting plain text into ciphertext. Each letter is represented by a number modulo 26. Though this is not an essential feature of the cipher, this simple scheme is often used:
<br>
Letter	A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z
<br>
Number	0	1	2	3	4	5	6	7	8	9	10	11	12	13	14	15	16	17	18	19	20	21	22	23	24	25
<br>
To encrypt a message, each block of n letters (considered as an n-component vector) is multiplied by an invertible n × n matrix, against modulus 26. To decrypt the message, each block is multiplied by the inverse of the matrix used for encryption.
<br>
The matrix used for encryption is the cipher key, and it should be chosen randomly from the set of invertible n × n matrices (modulo 26). The cipher can, of course, be adapted to an alphabet with any number of letters; all arithmetic just needs to be done modulo the number of letters instead of modulo 26.
<br>
The working is shown below:<br>
Input:<br>
1. Plain text that has to be converted into ciphertext.<br>
2. A KEY to encrypt the plain text<br>
Output: Ciphertext<br>

Formula : C = KPmod26<br>
C  is ciphertext, K is the key, P is the plain text vector.<br>
The KEY is generally given in the problem statement. Here we are considering a 2×2 matrix. The plain text vector is represented as a column matrices that are considered one at a time. Since the key matrix is 2×2, we take each column matrix as 2×1. If the key matrix was 3×3, then each column matrix would be 3×1.
let us take an example where plain text is ‘exam‘ which has to be converted to ciphertext with key-value as now, form the column matrices into 2×1 configurations and covert the text into numeric data assigning values to each alphabet from 0 to 25.<br>
a=0,b=1,c=2,d=3,………….,y=24,z=25
 
 
Consider the first column matrix and 
repeat this for second column matrix
  <br>
<b>Hence the final ciphertext is ‘elsc’</b>


<br>

# 2.Decryption – Cipher text to plain text
Decryption is the conversion of ciphertext into plain text. In order to decrypt, we turn the ciphertext back into a vector, then simply multiply by the inverse matrix of the key matrix. <br>
Formula :   P = (K’)(C) mod26<br>
where P is the plain text, K’ is the inverse key matrix, C is the ciphertext vector or the column matrices.<br>
Input: ciphertext and key<br>
Output: plain text.<br>
Here the C=’elsc’<br>
Now let us see the working:<br>
1. First, find the adjacent matrix of the given key matrix<br>
2. Find the determinant of the key matrix<br>
   77-88=-11<br>
3. Find the modulo of the determinant with 26<br>
    -11 mod26 =15=d<br>
4. Find the inverse number of the above result<br>
    (d x d’)mod26=1<br>
    (15 x d’)mod26=1 <br>
    d’=7<br>
5. Any negative numbers in K_adj should be moded by 26 and then the whole matrix 
    is multiplied by d’.<br>
Substituting all the values in the decryption formula, we get the required plain text.<br>
 
 
Repeat the above step using the other column matrix<br>
 
 
<b>Hence the final plain text is ‘exam’.</b>

# OUTPUT

<b>CASE1: (SUCCESSFUL)<b>

![image](https://user-images.githubusercontent.com/78469903/230756646-b662db30-2730-4907-8750-e72014b40c80.png)
![image](https://user-images.githubusercontent.com/78469903/230756682-d275effa-affb-4568-b163-699476dc64a4.png)
  
<br>
  
<b>CASE2: (UNSUCCESSFUL)<b><br>
![image](https://user-images.githubusercontent.com/78469903/230756694-279951fa-f0d3-4004-871b-c78be716f385.png)
![image](https://user-images.githubusercontent.com/78469903/230756706-1ce8a3c2-1885-4f8a-a3c8-7f36e84704f8.png)


