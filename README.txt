This program is a quantum-key exchange simulator. The inspiration for this program comes from Chapter 8 of a great book I read called "The Code Book" by Simon Singh, which details past, present and future cryptographic schemes and algorithms. 

There will come a time in the future when RSA can no longer be used as a secure key exchange algorithm due to the existence of quantum computers and the speed at which they are able to solve factorization problems. The following cryptographic algorithm can be used to securely exchange cryptographic keys using fundamental aspects of quantum mechanics surrounding measurement.

Imagine Alice and Bob want to exchange a binary message, a key. The message will be composed of ones and zeros which will represented by photons oriented in a certain manner respectively. When Alice sends the key to Bob, each photon can be transmitted with a rectilinear filter or a diagonal filter. For photons transmitted rectilinearly, a one is represented by a ↑ and a zero is represented by a → and the filter is represented by a 't'. Likewise, for photons transmitted diagonally, a one is represented by a ↗ and a zero is represented by a ↖ and the filter is represented by a 'x'. 

Alice will alter between the two possible filters randomly. Consider the following binary message: 

Message: 1 1 0 1 1 0 1 0 0 1
Filter:  t x t x x x t t x x
Result:  ↑ ↗ → ↗ ↗ ↖ ↑ → ↖ ↗

Let's say an eavesdropper were to try to intercept the message and read it. To measure the orientation of each photon, to see if it is a one or a zero, the eavesdropper needs to first decide on a filter to use for measurement for each photon in the stream. The evaesdropper doesn't know which filter Alice chose and will therefore have to pick at random and will therefore be wrong half the time. Think about it like so, the 't' filter can measure ↑ and → with certainty but cannot measure ↖ or ↗ with certainty because when the wave function collapses, the photon will be misinterpreted as vertically or horizontally oriented. Likewise, the 'x' filter can measure ↖ or ↗ with certainty but cannot measure ↑ and → with certainty because when the wave function collapses, the photon will be misinterpreted as a diagonally oriented. 

For example, if the 'x' detector is used to measure the first photon in the message above (↑), it will misinterpreted as ↖ or ↗. If it is misinterpreted as a ↗ then that's fine because it was intended to represent a one anyways. If it is misinterpreted as ↖ then that is an issue because the eavesdropped is led to believe that a zero was transmitted, which is incorrect. 

Bob is in the same dilemma as the evesdropper but this is where the magic happens. After the transmittion, Alice tells Bob which filter was used for the transmittion of each photon and they agree to only use only the ones where Bob picked the correct detector, so all of the misinterpreted photons are discarded. This is the purpose of the keyAgreement() function. 
