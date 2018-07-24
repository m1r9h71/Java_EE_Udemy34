# Java_EE_Udemy34
Using named queries to query by id
Inside FlightService is a new method:

    public void addPilotToFlight(String pilotId, String flightId) {

		TypedQuery<Flight> fQuery = em.createNamedQuery("Flight.findById", Flight.class);

		fQuery.setParameter("id", Integer.parseInt(flightId));

		Flight f = fQuery.getSingleResult();

		TypedQuery<Pilot> pQuery = em.createNamedQuery("Pilot.findById", Pilot.class);

		pQuery.setParameter("id", Integer.parseInt(pilotId));

		Pilot p = pQuery.getSingleResult();

	}
