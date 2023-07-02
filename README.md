# Quantum-Key-Distribution-Simulator

This program is a quantum-key exchange simulator (BB84). 

The inspiration for this program comes from chapter 8 of a great book I read called "The Code Book" by Simon Singh which details past, present and future cryptographic schemes and algorithms. 

There will come a time in the future when RSA can no longer be used for secure key exchange due to the existence of quantum computers and the speed at which they are able to solve factorization problems. The following key exchange scheme can be used to securely exchange keys using fundamental aspects of quantum mechanics surronding measurement.

Imagine Alice and Bob want to exchange a binary message, a key. The message will be composed of ones are zeros which will be represented by photons oriented in a certain manner up or down. When Alice sends the key to Bob, each photon can be transmitted with a rectinilear filter or a diagonal filter. For photons transmitted rectinilearly, a one is representated by a ↑, a zero is represented by a → and the filter is represented by a 't'. Likewise, for photons transmitted diagonally, a one is represented by a ↗, a zero is represented by a ↖ and the filter is represented by an 'x'. 

Alice will alter between the two filters randomly. Consider the following binary message:

![image](https://user-images.githubusercontent.com/44955493/157086582-20f75129-08f8-4461-98d8-04053d859839.png)

Let's suppose an eavesdropper (Eve for short) were to try to intercept the message and read it. To measure the orientation of each photon, to see if it is a one or zero, Eve needs to first decide on a filter to use for measurement for each photon in the stream. Eve doesn't know which filter Alice will chose and will therefore have to pick at random and will therefore pick incorrectly half of the time. The 't' filter can measure ↑ and → with certainity but cannot measure ↗ or ↖ with certainty because when the wave function collapses, the photon will be misinterpreted as vertically or horizontally oriented. Same logic can be applied to the 'x' filter.

For example, if the 'x' filter is used by Eve to measure the first photon in the message above ↑, it will be misread as as ↖ or ↗. If it misread as ↗ then that is fine for Eve since it was intended to represent a one anyways. If it is misread as ↖ then that is an issue for Eve since Eve is now under the impression that a zero was transmitted, which is incorrect. 

Bob is in the same dilemma as Eve but this is where a critical step takes place. After the transmittion, Alice tells Bob which filter was used for the transmittion of each photon and they agree to only use the ones where Alice and Bob picked the same detector. All of the misread photons are discarded which leaves them both with the same key. 

If the keys are different then they know that there was an eveasdropper on the line! They check this by exchanging a predetermined subset over the line. If this is the case they simply re-try transmittion.
