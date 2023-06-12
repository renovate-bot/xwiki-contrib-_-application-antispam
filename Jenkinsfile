/*
 * See the NOTICE file distributed with this work for additional
 * information regarding copyright ownership.
 *
 * This is free software; you can redistribute it and/or modify it
 * under the terms of the GNU Lesser General Public License as
 * published by the Free Software Foundation; either version 2.1 of
 * the License, or (at your option) any later version.
 *
 * This software is distributed in the hope that it will be useful,
 * but WITHOUT ANY WARRANTY; without even the implied warranty of
 * MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
 * Lesser General Public License for more details.
 *
 * You should have received a copy of the GNU Lesser General Public
 * License along with this software; if not, write to the Free
 * Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA
 * 02110-1301 USA, or see the FSF site: http://www.fsf.org.
 */

node('docker') {
    xwikiBuild {
        goals = 'clean deploy jacoco:report sonar:sonar'
        profiles = 'quality,integration-tests'
        sonar = true
        // Java 11+ is required for Sonar/Sonarcloud
        javaTool = 'java11'
        // We need a Maven version < 3.8.1 since Maven blocks external HTTP repositories by default since version 3.8.1
        // (see https://maven.apache.org/docs/3.8.1/release-notes.html). This can be removed oce the parent POM is
        // updated to a more recent XWiki version (13.10.11+ for example).
        mavenTool = 'Maven'
    }
}
