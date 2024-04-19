var SPHERE_CLASS = c => `class="sphere ${c || ''}"`
var SYSTEM_CLASS = c => `class="system ${c || ''}"`
var ORBIT_CLASS = c => `class="orbit ${c || ''}"`

function orbitTemplate(object, depth = 1) {
  var heading = `h${depth}`
  var list = depth % 2 ? 'ul' : 'ol'
  var style = `style="color: ${object[0].color || '#BDC5C7'}"`
  return `
    <${heading} ${style} ${SPHERE_CLASS()}>${object[0].name}</${heading}>
    ${ object[1] ? `
      <${list} ${SYSTEM_CLASS()}>
        ${ object[1].reduce((a, child) => a + `
          <li ${ORBIT_CLASS()}>${ orbitTemplate(child, depth + 1) }</li>
        `, '') }
      </${list}>
    ` : '' }
  `
}

function solarSystemData() {
  return [ { name: 'Sun', color: '#FDE528' }, [
    [ { name: 'Mercury', color: '#C1B4AC' } ],
    [ { name: 'Venus', color: '#F2D299' } ],
    [ { name: 'Earth', color: '#05f' }, [
      [ { name: 'Moon', color: '' } ]
    ] ],
    [ { name: 'Mars', color: '#E67E5A' }, [
      [ { name: 'Phobos', color: '' } ],
      [ { name: 'Deimos', color: '' } ]
    ] ],
    [ { name: 'Jupiter', color: '#C5AA96' }, [
      [ { name: 'Io', color: '' } ],
      [ { name: 'Europa', color: '' } ],
      [ { name: 'Ganymede', color: '' } ],
      [ { name: 'Callisto', color: '' } ]
    ] ],
    [ { name: 'Saturn', color: '#AF9D8E' }, [
      [ { name: 'Mimas', color: '' } ],
      [ { name: 'Enceladus', color: '' } ],
      [ { name: 'Tethys', color: '' } ],
      [ { name: 'Dione', color: '' } ],
      [ { name: 'Rhea', color: '' } ],
      [ { name: 'Titan', color: '' } ],
      [ { name: 'Iapetus', color: '' } ]
    ] ],
    [ { name: 'Uranus', color: '#C2E8EA' }, [
      [ { name: 'Miranda', color: '' } ],
      [ { name: 'Ariel', color: '' } ],
      [ { name: 'Umbriel', color: '' } ],
      [ { name: 'Titania', color: '' } ],
      [ { name: 'Oberon', color: '' } ]
    ] ],
    [ { name: 'Neptune', color: '#5C92F0' }, [
      [ { name: 'Triton', color: '' } ]
    ] ]
  ] ]
}

document
  .querySelector('.scene')
  .innerHTML = `
    <ul ${SYSTEM_CLASS()}>
      <li ${ORBIT_CLASS('top-most-orbit')}>
        ${ orbitTemplate(solarSystemData()) }
      </li>
    </ul>
  `