Question1:

The concept of RNG using a quantum system/concept to generate a random bitstring relies on using the superposition of the qubits. How?
Since the qubits state (o or 1) is random by itself by not even tring to make it random, so we can use this property to generate a bitstring.
So, the question is how to use this property? we've seen previously that using the gates to put the qubits in superposition such as Hamadar to put it onto superposition.
And then, we are going to measure it, so by that we are making it to go down or up (0 or 1).


Question2:

bitstring=[]
i=0
for i in range(1000):
    qreg = QuantumRegister(1)
    creg = ClassicalRegister(1)
    qc = QuantumCircuit(qreg, creg)
    qc.h(0)
    qc.measure(qubit=0, cbit=0)
    result = execute(qc, shots = 1000)
    value= [j for j in result if result[j]<500]
    if value != []:
        bitstring.append(value)
print(bitstring)
