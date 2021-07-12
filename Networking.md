# Networking Notes

*	Network: Multiple computers linked in order to share resources, exchange files, or allow electronic communication.

*	Basic Terms:
	*	Client: Machine accessing a service served by another machines i.e. server.
	*	Server: Machine or a software program running and serving a service to other machines i.e. clients.
	*	Host: Machine serving other clients.
	*	Bandwidth: Number of bits transferred over a network per second, measured in Kb/s, KB/s, Mb/s, MB/s, etc.
	*	Jitter: Time delay in sending of data packets over network.
	*	Packet: Network layer protocol data unit.
	*	Frame: Data link layer protocol data unit.
	*	LocalHost: The computer accessing services of itself.
	*	Bitrate: Speed of one specific connection between source and sink.
	*	Noise: Any undesired signal in a communication circuit.
	*	Attenuation: Loss of signal strength in networking cables or connections.
	*	Distortion: Interruption of transmitting signals that cause an unclear reception.

*	Web: Information system where resources can be located by their Uniform Resource Locators, and can be more complexed by using hyperlinks.
	*	Web vs Internet: Internet is infrastructure whereas web is a service running on that infrastructure.

*	Transmission Media: 
	*	Guided Media: High speed, Secure, Used for short distances.
		*	Twisted Pair Cable
			*	Unshielded: Cheap, Easy install, Slower speed than shielded ones, Susceptible to external interference, Slower than Shielded ones.
			*	Shielded: Expensive, Difficult install, Higher speeds, Bulky.
		*	Coaxial Cable: High bandwidth, Better noise immunity, Easy install, Cheap.
		*	Optical Fibre: High bandwidth, High speeds, Difficult install, Expensive, Fragile, Immune to electromagnetic waves.
	*	Unguided Media: Slower than guided ones, Less secure than guided ones, Used for larger distances.
		*	Transmitted through space by: 
			*	Radiowaves:
				*	Direction: Omni-directional.
				*	Penetration: Lower Frequencies - Yes, Higher Frequencies - No.
				*	Frequency Range: 3KHz to 1GHz.
				*	Security: Low.
				*	Attenuation: High.
				*	Government License: For some frequencies.
				*	Buy/Maintainence Cost: Moderate.
				*	Communication: Long distance.
			*	Microwaves:
				*	Direction: Uni-directional.
				*	Penetration: Lower Frequencies - Yes, Higher Frequencies - No.
				*	Frequency Range: 1GHz to 300GHz.
				*	Security: Medium.
				*	Attenuation: Variable.
				*	Government License: For some frequencies.
				*	Buy/Maintainence Cost: High.
				*	Communication: Long distance.
			*	Infrared:
				*	Direction: Uni-directional.
				*	Penetration: No.
				*	Frequency Range: 300 GHz to 400 GHz.
				*	Security: High.
				*	Attenuation: Low.
				*	Government License: Not required.
				*	Buy/Maintainence Cost: Cheap.
				*	Communication: Short distance.
*	Networking Devices: 
	*	Hub: Connects devices together at physical level without altering any packets, uses half-duplex connection.
		*	Passive Hub: Just connects devices.
		*	Active Hub: Connects devices & Strengthens/Concentrates the signal.
	*	Switch: Sends the data only to the receiver port using MAC addresses, works at data-link layer, uses full-duplex connection.
		*	Data Transfer Methods: 
			*	Cut-through transmission: Packet is sent asa. it is received, error checking is absent.
			*	Store & Forward transmission: Packet is checked when received and then sent, consumes bit of time to check.
			*	Fragment Free transmission: Packet's greater part is checked, after successful collision status, the packet is sent.
	*	Bridge: Connects two bridged networks using same protocol(eg: LAN) together.
		*	Transparent Bridge: Only blocks or forwards the data as per the MAC address, ignores other devices.
		*	Source Route Bridge: In this device, the path which packet takes through the network is implanted within the packet.
		*	Translational Bridge: Converts the data format of one networking to another.
	*	Router: 
