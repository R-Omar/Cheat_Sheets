

// template<int n>
// int& SequenceD<n>::operator[](int index)
// {	
// 	if (index >= sequence.size()) {
// 		throw runtime_error("SequenceD<n>::operator[] - index non valide");
// 	}
// 	return sequence[index];
// }

// template<int n>
// int SequenceD<n>::operator()(int index) const
// {
// 	if (index >= sequence.size()) {
// 		throw runtime_error("index non valide");
// 	}
// 	return sequence[index];
// }

// template<int n>
// SequenceD<n> SequenceD<n> :: operator*(SequenceD<n/2> s1 , SequenceD<n/2> s2){
// 	if (s1.size() != s2.size()) {
// 			throw runtime_error("tailles differentes des sequences");
// 		}
	
// 	SequenceD<n> result;
// 	result.sequence = s1.sequence * s2.sequence;
// 	result.sequenceD = s1.sequenceD * s2.sequenceD;
// 	return result;
// }






