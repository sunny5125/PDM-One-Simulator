/* 
 * Copyright 2008 TKK/ComNet
 * Released under GPLv3. See LICENSE.txt for details. 
 */
package routing;

import core.Connection;
import core.Settings;
import core.SimClock;

/**
 * Passive router that doesn't send anything unless commanded. This is useful
 * for external event -controlled routing or dummy nodes.
 * For implementation specifics, see MessageRouter class.
 */
public class PassiveRouter extends ActiveRouter {

	public PassiveRouter(Settings s) {
		super(s);
	}

	/**
	 * Copy-constructor.
	 * @param r Router to copy the settings from.
	 */
	protected PassiveRouter(PassiveRouter r) {
		super(r);
	}

	@Override
	public void update() {
		// nothing to update..
		
		if (SimClock.getIntTime() == 0)
		{
			System.out.println("$node(" + this.getHost().getAddress() + ") set X_ " + this.getHost().getLocation().getX());
			System.out.println("$node(" + this.getHost().getAddress() + ") set Y_ " + this.getHost().getLocation().getY());
		}
		else{
			System.out.println("$ns_ at " + SimClock.getTime() + " $node(" + this.getHost().getAddress() + ") set X_ " + this.getHost().getLocation().getX());
			System.out.println("$ns_ at " + SimClock.getTime() + " $node(" + this.getHost().getAddress() + ") set Y_ " + this.getHost().getLocation().getY());
		}
	}

	@Override
	public void changedConnection(Connection con) {
		/*
		if (con.isInitiator(getHost()))
		{
			if (con.isUp())
				System.out.println(SimClock.getTime() + " CONN UP " + getHost().getAddress() + " --> " + con.getOtherNode(getHost()));
			else
				System.out.println(SimClock.getTime() + " CONN DOWN " + getHost().getAddress() + " --> " + con.getOtherNode(getHost()));
		}
		*/
	}

	@Override
	public MessageRouter replicate() {
		return new PassiveRouter(this);
	}
}
